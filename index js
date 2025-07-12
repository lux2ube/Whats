const { Client, LocalAuth } = require('whatsapp-web.js');
const qrcode = require('qrcode-terminal');

// Use persistent session storage
const client = new Client({
    authStrategy: new LocalAuth()
});

// QR code event
client.on('qr', (qr) => {
    console.log('Scan this QR code with your WhatsApp:');
    qrcode.generate(qr, { small: true });
});

// Ready event
client.on('ready', () => {
    console.log('✅ WhatsApp bot is ready!');
});

// Message handler
client.on('message', async (msg) => {
    if (msg.body.toLowerCase() === '!ping') {
        await msg.reply('Pong 🏓');
    }
});

client.initialize();
