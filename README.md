# My Baileys

<p align="center">
  <img src="https://files.catbox.moe/qlbg31.jpg" alt="Thumbnail" width="400" />
</p>

<p align="center">
  <img src="https://media.giphy.com/media/jn7s8n5dLrJzazg7nN/giphy.gif" width="280"/>
</p>

---

## Tentang Project
**My Baileys** adalah bot WhatsApp berbasis [Baileys](https://github.com/WhiskeySockets/Baileys).  
Dibuat dengan fokus pada performa, stabilitas, dan fleksibilitas agar dapat digunakan untuk berbagai kebutuhan, mulai dari personal hingga komunitas.

---

## Fitur Utama
- Multi Device support (WhatsApp MD).
- Pairing Code dan QR Login.
- Dukungan tema dan tampilan custom.
- Fitur lanjutan seperti ForceCall, Carousels, dan Native Flow.
- API server menggunakan Express.
- Optimized crash handler.

---

## Instalasi
```bash
# Clone repository
git clone https://github.com/username/my-baileys.git

# Masuk ke folder
cd my-baileys

# Install dependencies
npm install

# Jalankan bot
node index.js           renderLargerThumbnail: false         
        },
        buttons: [
            {
                name: "cta_url",
                buttonParamsJson: JSON.stringify({
                    display_text: "Telegram",
                    url: "https://t.me/stvnnvs",
                    merchant_url: "https://t.me/stvnnvs"
                })
            }
        ]
    }
}, { quoted: m });
```

### Interactive Message with Document Buffer (Simple)
Send interactive messages with document from buffer (file system) without contextInfo and externalAdReply - **Note: Documents only support buffer**:

```javascript
await sock.sendMessage(jid, {
    interactiveMessage: {
        title: "Hello World",
        footer: "telegram: @stvnnvs",
        document: fs.readFileSync("./package.json"),
        mimetype: "application/pdf",
        fileName: "stvnnvs.pdf",
        jpegThumbnail: fs.readFileSync("./document.jpeg"),
        buttons: [
            {
                name: "cta_url",
                buttonParamsJson: JSON.stringify({
                    display_text: "Telegram",
                    url: "https://t.me/stvnnvs",
                    merchant_url: "https://t.me/stvnnvs"
                })
            }
        ]
    }
}, { quoted: m });
```

### Request Payment Message
Send payment request messages with custom background and sticker:

```javascript
let quotedType = m.quoted?.mtype || '';
let quotedContent = JSON.stringify({ [quotedType]: m.quoted }, null, 2);

await sock.sendMessage(jid, {
    requestPaymentMessage: {
        currency: "IDR",
        amount: 10000000,
        from: m.sender,
        sticker: JSON.parse(quotedContent),
        background: {
            id: "100",
            fileLength: "0",
            width: 1000,
            height: 1000,
            mimetype: "image/webp",
            placeholderArgb: 0xFF00FFFF,
            textArgb: 0xFFFFFFFF,     
            subtextArgb: 0xFFAA00FF   
        }
    }
}, { quoted: m });
```

---

## Why Choose WhatsApp Baileys?

Because this library offers high stability, full features, and an actively improved pairing process. It is ideal for developers aiming to create professional and secure WhatsApp automation solutions. Support for the latest WhatsApp features ensures compatibility with platform updates.

---

### Technical Notes

- Supports custom pairing codes that are stable and secure
- Fixes previous issues related to pairing and authentication
- Features interactive messages and action buttons for dynamic menu creation
- Automatic and efficient session management for long-term stability
- Compatible with the latest multi-device features from WhatsApp
- Easy to integrate and customize based on your needs
- Perfect for developing bots, customer service automation, and other communication applications

---

For complete documentation, installation guides, and implementation examples, please visit the official repository and community forums. We continually update and improve this library to meet the needs of developers and users of modern WhatsApp automation solutions.

**Thank you for choosing WhatsApp Baileys as your WhatsApp automation solution!**
