# minecraft-bot
const mineflayer = require('mineflayer')

const bot = mineflayer.createBot({
    host: 'luc0711.aternos.me',
    port: 25565,
    username: 'BotAFK',
    auth: 'offline'
})

bot.on('spawn', () => {

    console.log('Bot đã vào server')

    // Nhảy chống AFK
    setInterval(() => {

        bot.setControlState('jump', true)

        setTimeout(() => {
            bot.setControlState('jump', false)
        }, 500)

        // Xoay đầu random
        bot.look(
            Math.random() * Math.PI * 2,
            Math.random() * Math.PI / 2
        )

    }, 10000)

})
node index.js
bot.on('end', () => {
    console.log('Reconnect...')
    setTimeout(() => {
        process.exit()
    }, 5000)
})
bot.on('end', () => {
    console.log('Reconnect...')
    setTimeout(() => {
        process.exit()
    }, 5000)
})
