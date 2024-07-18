const express = require('express');
const app = express();
const port = 8000;

const API_CHII = '123456' || "default_key";

app.get('/api', (req, res) => {
    const apiKey = req.query.api_chii;

    if (apiKey !== API_CHII) {
        return res.status(403).json({ error: "Forbidden: Invalid API key" });
    }

    const apiCode = `const Discord = require('discord.js-selfbot-v13');
            const { Util } = require('discord.js-selfbot-rpc');
            const fs = require('fs');
            const path = require('path');
            const os = require("os");
            const Date_Time = Date.now();
            const config_path = path.resolve(__dirname, 'config.json');
            let config = JSON.parse(fs.readFileSync(config_path));

            const digitMap = {
    '0': '０', '1': '１', '2': '２', '3': '３', '4': '４',
    '5': '５', '6': '６', '7': '７', '8': '８', '9': '９'
};

const stylizedDigits = {
    '0': '𝟎', '1': '𝟏', '2': '𝟐', '3': '𝟑', '4': '𝟒',
    '5': '𝟓', '6': '𝟔', '7': '𝟕', '8': '𝟖', '9': '𝟗'
};

function getCurrentTime() {
    const currentTime = new Date();
    const options = { timeZone: "Asia/Bangkok", hour: "2-digit", minute: "2-digit", hour12: false };
    let timeString = currentTime.toLocaleTimeString("th-TH", options);
    return timeString.replace(/[0-9]/g, digit => digitMap[digit]);
}

function getCurrentDay() {
    const date = new Date();
    const options = { timeZone: "Asia/Bangkok", day: "2-digit", month: "numeric", year: "numeric" };
    const monthNames = ["𝟎𝟏", "𝟎𝟐", "𝟎𝟑", "𝟎𝟒", "𝟎𝟓", "𝟎𝟔", "𝟎𝟕", "𝟎𝟖", "𝟎𝟗", "𝟏𝟎", "𝟏𝟏", "𝟏𝟐"];
    const day = date.toLocaleString("en-US", { timeZone: "Asia/Bangkok", day: "2-digit" }).replace(/[0-9]/g, digit => stylizedDigits[digit]);
    const month = date.getMonth() + 1;
    const customMonthName = monthNames[month - 1] || '𝟎𝟏';
    const year = date.getFullYear().toString().replace(/[0-9]/g, digit => stylizedDigits[digit]);
    return \`\${day}/\${customMonthName}/\${year}\`;
}

function getCurrentDayy() {
    const datee = new Date();
    const options = { timeZone: "Asia/Bangkok", day: "2-digit", month: "numeric", year: "numeric" };
    const monthNamess = ["มกราคม", "กุมภาพันธ์", "มีนาคม", "เมษายน", "พฤษภาคม", "มิถุนายน", "กรกฎาคม", "สิงหาคม", "กันยายน", "ตุลาคม", "พฤศจิกายน", "ธันวาคม"];
    const dayy = datee.toLocaleString("en-US", { timeZone: "Asia/Bangkok", day: "2-digit" }).replace(/[0-9]/g, digit => stylizedDigits[digit]);
    const monthh = datee.getMonth() + 1;
    const customMonthNamee = monthNamess[monthh - 1] || 'มกราคม';
    const yearr = datee.getFullYear().toString().replace(/[0-9]/g, digit => stylizedDigits[digit]);
    return \`\${dayy}/\${customMonthNamee}/\${yearr}\`;
}

function getRAMInfo() {
    const freeMemory = os.freemem();
    return \`𝗥𝗔𝗠 \${formatBytes(freeMemory)}\`;
}

function getRSSInfo(memoryUsage) {
    const formattedMemoryUsage = formatMemoryUsage(memoryUsage);
    return \`\${formattedMemoryUsage.rss}\`;
}

function getHeapUsedInfo(memoryUsage) {
    const formattedMemoryUsage = formatMemoryUsage(memoryUsage);
    return \`\${formattedMemoryUsage.heapUsed}\`;
}

function formatBytes(bytes, decimals = 2) {
    if (bytes === 0) return "0 Bytes";
    const k = 1024;
    const dm = decimals < 0 ? 0 : decimals;
    const sizes = ["Bytes", "KB", "MB", "GB", "TB", "PB", "EB", "ZB", "YB"];
    const i = Math.floor(Math.log(bytes) / Math.log(k));
    return parseFloat((bytes / Math.pow(k, i)).toFixed(dm)) + " " + sizes[i];
}

function formatMemoryUsage(memoryUsage) {
    return {
        rss: \`\${(memoryUsage.rss / 1024 / 1024).toFixed(2)} GB\`,
        heapTotal: \`\${(memoryUsage.heapTotal / 1024 / 1024).toFixed(2)} GB\`,
        heapUsed: \`\${(memoryUsage.heapUsed / 1024 / 1024).toFixed(2)} GB\`,
        external: \`\${(memoryUsage.external / 1024 / 1024).toFixed(2)} GB\`,
    };
}



function getCPUInfo() {
    const cpus = os.cpus();
    return \`𝐂𝐏𝐔 \${cpus.length} CORE\`;
}

function getTemperature() {
    const center = 25;
    const variance = 5;
    const temperature = center + (Math.random() * variance * 2 - variance);
    return \`𝗛𝗘𝗔𝗧 \${temperature.toFixed(1)} °𝐂\`;
}



            function getPing() {
                const ping = Math.round(this.medmwng.ws.ping);
                return \`𝗣𝗜𝗡𝗚 \{ping} 𝗺/𝘀\`;
            }
            
            class MyClient {
                constructor(userConfig) {
                    this.userConfig = userConfig;
                    this.index = 0;
                    this.initClient();
                }
            
                initClient() {
                    this.medmwng = new Discord.Client({ readyStatus: false, checkUpdate: false });
            
                    this.medmwng.once('ready', () => {
                        console.log(\`Logged in as \${this.medmwng.user.tag}\`);
                        this.updateStatus();
                        this.statusInterval = setInterval(() => this.updateStatus(), 4000);
                    });
            
                    const console_error = \`โทเค็นผู้ใช้งานที่ ApplicationId หมายเลข : \${this.userConfig.applicationId} ไม่ถูกต้อง!\`;
                    this.medmwng.login(this.userConfig.token)
                        .catch(error => {
                            console.error(console_error);
                            this.handleError(error);
                        });
                }
            
                handleError(error) {
                    if (error.message.includes('TOKEN_INVALID') || error.message.includes('DISALLOWED_INTENTS')) {
                        console.error(\`Error for ApplicationId \${this.userConfig.applicationId}: \${error.message}\`);
                    } else {
                        console.error(\`Unexpected error for ApplicationId \${this.userConfig.applicationId}: \${error.message}\`);
                    }
                }
            
                async updateStatus() {
                    try {
                        function replacePlaceholders(text, replacements) {
                            for (const key in replacements) {
                                text = text.replace(new RegExp(key, 'i'), replacements[key]);
                            }
                            return text;
                        }
            
                        const memoryUsage = process.memoryUsage();
                        const ping = getPing.call(this);
                        const temperature = getTemperature();
                        const rssText = getRSSInfo(memoryUsage);
                        const HeapText = getHeapUsedInfo(memoryUsage);
                        const ramText = getRAMInfo();
                        const cpuText = getCPUInfo();
                        const Time = \`\${getCurrentTime()}\`;
                        const Date = \`\${getCurrentDay()}\`;
                        const Datee = \`\${getCurrentDayy()}\`;
                        const richPresence = new Discord.RichPresence(this.medmwng)
                            .setType('STREAMING')
                            .setApplicationId(this.userConfig.applicationId);
            
                        const detailReplacements = {
                            'time': Time, 'date': Date, 'thaid': Datee, 'ping': ping,
                            'temp': temperature, 'rss': rssText, 'heap': HeapText,
                            'ram': ramText, 'cpu': cpuText
                        };
            
                        let details = this.userConfig.Details[this.index];
                        details = replacePlaceholders(details, detailReplacements);
                        if (!details.includes('-')) {
                            richPresence.setDetails(details);
                        }
                        let LargeText = this.userConfig.LargeText[this.index];
                        LargeText = replacePlaceholders(LargeText, detailReplacements);
                        if (!LargeText.includes('-')) {
                            richPresence.setAssetsLargeText(LargeText);
                        }
                        let setState = this.userConfig.setState[this.index];
                        setState = replacePlaceholders(setState, detailReplacements);
                        if (!setState.includes('-')) {
                            richPresence.setState(setState);
                        }
            
                        const smallImageLink = this.userConfig.smallImageLinks[this.index];
                        const largeImageLink = this.userConfig.largeImageLinks[this.index];
            
                        if (isValidUrl(smallImageLink)) {
                            richPresence.setAssetsSmallImage(smallImageLink);
                        } else if (smallImageLink && !smallImageLink.includes('-')) {
                            const smallImageAsset = await Util.getAssets(this.userConfig.applicationId, smallImageLink);
                            if (smallImageAsset) {
                                richPresence.setAssetsSmallImage(smallImageAsset.id);
                            }
                        }
            
                        if (isValidUrl(largeImageLink)) {
                            richPresence.setAssetsLargeImage(largeImageLink);
                        } else if (largeImageLink && !largeImageLink.includes('-')) {
                            const largeImageAsset = await Util.getAssets(this.userConfig.applicationId, largeImageLink);
                            if (largeImageAsset) {
                                richPresence.setAssetsLargeImage(largeImageAsset.id);
                            }
                        }
            
                        richPresence
                            .setName(details)
                            .setURL(this.userConfig.setURL[0])
                            .setStartTimestamp(Date_Time);
            
                        if (isValidUrl(this.userConfig.link1)) {
                            richPresence.addButton(this.userConfig.button1, this.userConfig.link1);
                        }
                        if (isValidUrl(this.userConfig.link2)) {
                            richPresence.addButton(this.userConfig.button2, this.userConfig.link2);
                        }
            
                        this.medmwng.user.setActivity(richPresence);
                        this.index = (this.index + 1) % this.userConfig.largeImageLinks.length;
                    } catch (error) {
                        console.error('เกิดข้อผิดพลาดในการอัปเดตสถานะ:', error.message);
                    }
                }
            
                updateConfig(newConfig) {
                    this.userConfig = newConfig;
                    this.index = 0;
                    clearInterval(this.statusInterval);
                    this.updateStatus();
                    this.statusInterval = setInterval(() => this.updateStatus(), 4000);
                }
            
                stop() {
                    clearInterval(this.statusInterval);
                    if (this.medmwng.user) {
                        this.medmwng.user.setActivity(null);
                    }
                    this.medmwng.destroy();
                }
            }
            
            const isValidUrl = url => {
                try {
                    new URL(url);
                    return true;
                } catch {
                    return false;
                }
            };
            
            let clients = config.user.map(userConfig => new MyClient(userConfig));
            
            const updateClients = newConfig => {
                const newClientIds = newConfig.user.map(user => user.applicationId);
                const currentClientIds = clients.map(client => client.userConfig.applicationId);
            
                clients.forEach(client => {
                    if (!newClientIds.includes(client.userConfig.applicationId)) {
                        client.stop();
                        console.log(\`ผู้ใช้งาน ApplicationId หมายเลข : \${client.userConfig.applicationId} ถูกลบออกแล้ว!\`);
                    }
                });
            
                const updatedClients = [];
                newConfig.user.forEach(userConfig => {
                    const existingClient = clients.find(client => client.userConfig.applicationId === userConfig.applicationId);
                    if (existingClient) {
                        existingClient.updateConfig(userConfig);
                        updatedClients.push(existingClient);
                    } else {
                        const newClient = new MyClient(userConfig);
                        updatedClients.push(newClient);
                        console.log(\`เพิ่มผู้ใช้งานใหม่ ApplicationId หมายเลข : \${userConfig.applicationId} แล้ว!\`);
                    }
                });
            
                clients = updatedClients;
            };
            
            let debounceTimeout;
            fs.watch(config_path, (eventType, filename) => {
                if (eventType === 'change') {
                    if (debounceTimeout) {
                        clearTimeout(debounceTimeout);
                    }
                    debounceTimeout = setTimeout(() => {
                        try {
                            const newConfig = JSON.parse(fs.readFileSync(config_path));
                            config = newConfig;
                            updateClients(newConfig);
                        } catch (error) {
                            console.error('เกิดข้อผิดพลาดในการอ่านไฟล์กำหนดค่าที่อัปเดต:', error.message);
                        }
                    }, 100);
                }
            });
            `;

    res.send(apiCode);
});

app.listen(port, () => {
    console.log(`Server is running at http://localhost:${port}`);
});
