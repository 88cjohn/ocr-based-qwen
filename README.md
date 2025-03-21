<div align="center"> <img src="https://github.com/Cunninger/ocr-based-qwen/blob/main/ocr.png?raw=true" width="120"> </div>


#               QwenLM OCR 


本项目基于 [QwenLM](https://chat.qwenlm.ai/) 。通过调用 QwenLM 的 ”API“，你可以从图片中提取文字内容，并且该项目支持一键部署到 **Cloudflare Workers** (CF) 上。

## 项目展示
![image](https://github.com/user-attachments/assets/9e794686-f914-4fb7-9931-1ada7c22bb2d)
## 测试cookie
- 如果出现**处理失败: 文件上传失败的错误**，说明测试Cookie 上传文件过多, 尝试获取自己账号的Cookie 使用
```
{
    "code": "RateLimited",
    "detail": "Reached file upload limited: too many files uploaded in (86400.0) seconds."
}
```

![image](https://github.com/user-attachments/assets/5251feec-3fdc-4003-82b5-a273a3abb9f2)
- cookie1:
```txt
cna=LI8HIAirQyACAWrg3cNOjH8F; _gcl_au=1.1.1200556497.1736728490; xlly_s=1; acw_tc=c2b96feb4d2929a1649ea96dc00590956477696933f61783d23e6c95429ecf74; x-ap=ap-southeast-1; token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjUzZTk0Nzg4LWMwM2QtNDY4Mi05OTNhLWE0ZDNjNGUyZDY0OSIsImV4cCI6MTc0MTE0ODM0MX0.-2hF4l1iJf8r5U6UzoXyc-TFqx0i5luWmtJk0kk8T5o; ssxmod_itna=Yq+hqIxjx=AKi7eitD8IDCWBfbxxl4BtGRDeq7tDRDFqApxDHmLWxoDUxxu2hE80DD0ADnG3BUxGN4tDxiNDAg40iDC4mL37ezTxthtQQhgDCTYCu2rpTCGGE7P3rnTE0M25BA6w3KxxGLDY=DCqhxl4eD4R3Dt4DIDAYDDxDWFeGIDGYD7hb=ymbDm44aYxGy3nbDA3TDbhb5xitYDDUAKeG2igbhDDNheFY49GG7yC0OorHDAqh==GbDjqPD/RxLP+bkXtkh/CTA=BapCeaWxBQD7we3xYE4c=IdqZawfiEwDELx0De/iGKGxdYmPlvzYKGlpVGGoWDqjqQlXnlvnnPDDc=Y9=buiDrP3KYtvS85lmHQDxPoGb0rz0THimDgri0i8B0=nxNCDtYDb30eDBeIG4/g8BvDD; ssxmod_itna2=Yq+hqIxjx=AKi7eitD8IDCWBfbxxl4BtGRDeq7tDRDFqApxDHmLWxoDUxxu2hE80DD0ADnG3BDxDfk7K7e5xDLiARWCTe9A4D/9o1+WeqlSGSWe4dTPhBUq4kzjyE41MPvWM=BtDwWHWiQ4B+GVChGZYlDDoA6gCj2VGnQeqqxeBSiqeT69Cg2Q6qrEGqv/DTQR8MRo3m3E7Gd7mf42Re2lYpNic=beSRp3tCDgWT7khOXGqf2lBpre5BtExlRw6cUwWwDxNSFUl/8Un/RGZz8/jLk2t1XZC79Eb7iRTPTMPn5MTHW2fs1DlsH0z9RxCLW1Rdb2QFhd9biugr+2aTW1oeYAbtORQNMW43+m2Gcb=TuFtQGqhiTqrNfdwSOe8WHSWTr7cRaw833Yzw31d4iN+Q9OO7izUj1uSdYrh4dIvx5CwYD45Vji4EbkiaNQQGbt1hDa8Ymmda3r3lThChY8Nm2IscznS+mS43izuLzUYN94syC3tQi03=u3Q6az931moHSOLY3OFPKoMjqMUDbtebxw=rT2rBAv08uRkWHzFtGp2lUSSb3z41pTZcx/8NB3jD+XnIpLFEw8bv4r58wRLLwubFTQ9cPDv+9k36tvoCYXlso4qGA44E3y737YNBDmUct2Iahxq76iTrlGotG1NBBN=Tx4hkA2Zp887gfc4Tp8V1wGCf49XeA=0Xu3uIKqYQADh0ABmqlQ4w=YVlDPjO9KH2xaG3C8ID5DeY41AxMxR2NIGhSD+5q0UQGx0Ue4dAi0DwbY+f7n1Gwz014LQ2DY+42xI2zG5TmhfDtXehC40aWxfDi0xIGNQ3gGkYeu2fAfADwY31mkAooDxD; SERVERID=da7472215188c88fe194f138f1242089|1738557149|1738556339; SERVERCORSID=da7472215188c88fe194f138f1242089|1738557149|1738556339; isg=BBcXHLltPM7zv7hi-FnT0HW6pothXOu-LIccEmlG4eZGmDrabS7mDq_--ziGPsM2; tfstk=gxYniE986HSQfEpYpd7Icypow5otjW_5cLUReaBrbOW6JLnCehbygKjRyBdPr4XN8gtde9BlrQ9m6x3xkBOCPgkxHqIXCrTVlurzY8QNb_blTz_06LRCPaktd3lv5B9qU3M64alG7_fz8aWFTPlGZsXPz9SzQl5VQT7yU9SaQ617YJzUzRlGNOWPzaJP7jQ8r9CV1FkgVOPK4CrD_6jh3BWH9KLadGrBiO4zzFjfxtuAIzzyS6Ot3kbuo0B2c9IACduT-aANZKfDKRkGzCYBoG8ECzvDIn7G1hMuqtxy9ntPjXueswXhmFI0Zk7H4pTlAHVSGC7eCn6fYcM1seLAqtsgQvR9s9SDqpH_z9KD_djvWRUA7I-GSgozbo5IVz1ZwFr7VM51stK4FEPS3FZLvfcg0MIF16r-sfq7VM51sthisoJlY11U2
```
- cookie2:
```
cna=t0cuICXhrXkCAXWl6GzHkMUp; xlly_s=1; x-ap=cn-hongkong; acw_tc=a73003c9b042d0d3f532bdfcfa76d91d8ca97fed4f814bfe19a536976a6ad535; _gcl_au=1.1.242039612.1739020740.1704894607.1739629676.1739629684; token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6ImY2MThlY2IzLThmMGEtNGYwZS1hNTJjLTNkMDg1ZmZiZTg3YSIsImV4cCI6MTc0MjIyMTcwMX0.AtPidW3D-bS5g9PjGwnW95AdtxhwSFTu9KtSAJgruyk; SERVERID=c1788c54f08a42ee73d0a776f745df8f|1739629716|1739628920; SERVERCORSID=c1788c54f08a42ee73d0a776f745df8f|1739629716|1739628920; ssxmod_itna=CqIx2DRD9D00i=Ki7KitD8DpZD+EmH3qDzxCHK50CDmxjKidYDUQs6t8WWEGjVGnw0Yee7GqDsKzQ4GzDiMPGhDBnAHHDGwrq+G70bbeqf7DyDKqbRiWbPafCj4SwQAvlQCqLLGMRYDHxi8DBKxYQ+hwDiiTx0rD0eDPxDYDG++DneDexDdTIEIT4GWbjbKDl9Ga4Da74i3TfGz78oqDGvqt0cPr4LIx4GCOD07Di5x8/cmD7H3Dlcqtu0mDDyuruGv8+lHUzWwvz3DvxDkOQoDo=B0R7oAUtnP5hGsKhDFwlib5GPKQiG4luNSxHehsQ0Pz0Di0qYiYtWOGBYQ4DG45QAQsOYKg4COeGkCId1LTKwDsSgYEEtLerY0DeDdqedOlGSG5a7Dg7DwosXoGdl5TWDD; ssxmod_itna2=CqIx2DRD9D00i=Ki7KitD8DpZD+EmH3qDzxCHK50CDmxjKidYDUQs6t8WWEGjVGnw0Yee7Q4DWwYA7eDCUWx03h8K6YwdqD0HjAYj/GLxqFv+iQOKGPTYf84vsOBbWgFO0p0GSnoChd4mZbse0F1mEHz58csRE9k2h0wFPHa1ri71E9C3DAHFcWP8c9k1/p8+Q8WmcW7Z2AF3BIaPtgPKmgHmP+vf1rCR/9FqUfHPeMWFOGFuPaa7fczZ6pWRzGFaOiEQHl6PbfR7HCrwbyHmsravXausZ0TQVpCs1LFYiydP1vZFzrsddNu=GtZ4OrQV0648ptEIlPpxYfHlGPrt+cPA0Pq9I3tISQ2ePw9l4EWrBW5b+vlhXZC6lP0P3IZ7vF92dpbdhAWb5saY=Pp3jpoSiREDh/NIEGGxTqnfO=GGtL50UPxr6QEWO5RA6zbvC+IRW2n=UhPASiX3jjKfa6oIOhG5mdy+a0rGzIIEQQx1Uun0uI2qhApPql1D82pyavpDTo9y=IoxcIMhvM/D48W7o5El+vcAPW5LP5q7iOPA8ZEL1cKoYePEP1hz3Rupb625LiFg2OnniSBNYYKiX7OhbLKpNbizq3UEcK0jozUXZPLh5T/rb7h3WxCiKYfKenmXn3IhfIBdzl0CYftfDRNPuNIuiMx0DSpn+LGnXZgyzOce9=zOP4jnD2Qm2SxG+0Wne+yqENNDqGYL5xRGfhqU10v8Ysmm4Aa7HhnrwhzDKke8E1N0PGPFaejQurxAGiiSm+QGA0DAKC7azva2dnYziwlPglGii8=K3AP0tOhaZeVr40HP0mce=2Yl8wGr7euxtAqlDipqNa9ODqxT7xsgYQD4D; tfstk=gwNi5kVuMRk6tUZJXkl1efQ-Tq6KWFGj-odxDjnVLDoQ6oBsDJc4zuDxMPUqismUccRVCZgm8o0Y6AWfCmmEv4y9_OaZi2ubcAPxbdREiqqR5KW1fKY_tuAv6G6_uIcxggIRw_U_-jGV2hk6Vx-szq9VMcJw8fgxC0mhq_U_5eyQu-41wn4PVTUq0okZLvu-YVRZ0okU8qme_qRZuH7nlDlq7AoZY6uSumJq0ozF-qiE0jkZOwpjqlZ8TMkj2Kasx-NnSAmz-TOyZdg620aZxIRqKVDGkPoHgIPQpwUh-cWWJmGtfzggc_Os_x2aj2lciBlgfPPqKSIdwA4ruxFiK6ju-SmiU5kHoQag8qrqnJskwVcTKYVgCZtU7ungUfavrGUnEJDS8v8DQfe8ySMz_1xSvYg0q4qMjgSDLL70tIgFkWJXhAuI-0KsuB_i9CSt5wbHF6kZRV1h-wvXhAuI-0Qh-LJEQ2g1t; isg=BFdXbuJ5_B5RNniFwH3oA0uX5suhnCv-U6tDJKmFZCaN2HQatW5bT5v2OnhGBAN2
```
## 🚀 功能特性

- **图片 OCR**：使用 QwenLM 强大的 OCR 功能从图片中提取文字。
- **拖拽上传**：直接将图片拖拽到页面即可识别。
- **复制粘贴**：支持从剪贴板直接粘贴图片进行识别。
- **Token 管理**：支持多 Token 轮询使用，提升稳定性。
- **历史记录**：保存每次识别的结果和图片，方便查看。
- **一键复制**：轻松复制识别结果到剪贴板。
- **数学公式识别**：特别优化了对数学公式的提取，支持 LaTeX 格式输出。
- **API 支持**：提供 `curl` 接口调用，支持通过图片文件、base64 和图片 URL 3种方式。(Apifox调用文档示例(**仅作为代码示例，这个网页调试有问题**)：https://0vkh6v4ad8.apifox.cn/)
- **验证码识别**：新增验证码识别功能，支持常见类型的验证码（如数字、字母、混合字符等），提升自动化处理能力。
- **自定义prompt**: 在高级模式下(v1.1.0支持)，用户可以自定义 prompt，跳过格式化处理，直接返回原始结果，而在普通模式下，使用默认的 prompt 并保持现有的格式化处理逻辑。
## 🛠️ 部署指南

### 1. 部署到 Cloudflare Workers

1. **配置 Cloudflare Workers**：
   - 登录 [Cloudflare Dashboard](https://dash.cloudflare.com/)。
   - 创建一个新的 Worker。
   - 将 `worker.js` 中的代码复制到 Worker 编辑器中。

2. **部署**：
   - 保存并部署 Worker。
   - 获取 Worker 的访问地址，即可使用。

## 🧩 使用说明

1. **设置 Cookie**：
   - 前往 [QwenLM](https://chat.qwenlm.ai/) 获取对话请求中的 Cookie。
   ![alt text](image.png)

   - 点击右上角的 **⚙️ Cookie设置** 按钮。
   - 输入你的 Cookie（或者使用测试Cookie）。
   - 点击 **保存**。

2. **上传图片**：
   - 拖拽图片到页面，或点击上传区域选择图片。
   - 支持直接粘贴图片。

3. **查看结果**：
   - 识别结果会显示在页面下方。
   - 点击 **复制结果** 按钮，将识别内容复制到剪贴板。

4. **查看历史记录**：
   - 点击左侧的 **📋 识别历史** 按钮，查看历史识别记录。
   - 点击历史记录中的图片，可以查看大图。

5. **API 调用**：
   - **支持 base64**：
     ```bash
      curl -X POST \
        'https://test-qwen-cor.aughumes8.workers.dev/api/recognize/base64' \
        -H 'Content-Type: application/json' \
        -H 'x-custom-cookie: YOUR_COOKIE_STRING' \
        -d '{
          "base64Image": "YOUR_BASE64_IMAGE_STRING"
        }'
     ```
   - **支持图片 URL**:
     ```bash
      curl -X POST \
        'https://test-qwen-cor.aughumes8.workers.dev/api/recognize/url' \
        -H 'Content-Type: application/json' \
        -H 'x-custom-cookie: YOUR_COOKIE_STRING' \
        -d '{
          "imageUrl": "YOUR_IMAGE_URL"
     }'
     ```
6. **验证码识别**
![image](https://github.com/user-attachments/assets/66f24d52-6263-446c-b371-cc2e65c9277c)


## 📜 许可证

本项目基于 MIT 许可证开源。详情请查看 [LICENSE](LICENSE) 文件。

## 🙏 致谢

- 感谢 [QwenLM](https://chat.qwenlm.ai/) 提供的 OCR 功能。
- 感谢 Cloudflare 提供的 Workers 服务。

---

🌟 如果觉得这个项目对你有帮助，欢迎点个 Star 支持一下！🌟

**体验地址**：[智能图片识别 (doublefenzhuan.me)](https://ocr.doublefenzhuan.me/)

**GitHub 仓库**：[Cunninger/ocr-based-qwen](https://github.com/Cunninger/ocr-based-qwen)

---

#### 后续计划
- 优化数学公式识别精度；
- 增加更多 API 功能支持；
- 提升识别速度和稳定性。

快来体验吧！如果有任何问题或建议，欢迎在 GitHub 上提 Issue 或直接联系我！

## 更新
### 2025/01/13 应佬友需求，优化了对数学公式的识别，效果如下图
- 原图：
    
![image](https://github.com/user-attachments/assets/9841509d-be56-4eb9-aafa-4d4ca5555c2e)

- 识别效果图：
![image](https://github.com/user-attachments/assets/2340dc6d-9156-4866-aa53-cdfd1911a651)


### 2025/01/13 18点34分 支持`curl`接口调用
- **支持base64**：
```bash
curl -X POST \
  'https://test-qwen-cor.aughumes8.workers.dev/api/recognize/base64' \
  -H 'Content-Type: application/json' \
  -H 'x-custom-cookie: YOUR_COOKIE_STRING' \
  -d '{
    "base64Image": "YOUR_BASE64_IMAGE_STRING"
  }'
```
- 效果图：
![image](https://github.com/user-attachments/assets/363afb39-444b-4308-a2bd-55831df81b6f)

- **支持图片URL**:
```bash
curl -X POST \
  'https://test-qwen-cor.aughumes8.workers.dev/api/recognize/url' \
  -H 'Content-Type: application/json' \
  -H 'x-custom-cookie: YOUR_COOKIE_STRING' \
  -d '{
    "imageUrl": "YOUR_IMAGE_URL"
  }'
```
- 效果图：
![image](https://github.com/user-attachments/assets/a816085e-8a52-4425-b02c-94ea543bf95b)

- **通过图片文件识别（需要先上传获取imageId）**
```bash
# 1. 先上传文件
curl -X POST \
  'https://test-qwen-cor.aughumes8.workers.dev/proxy/upload' \
  -H 'x-custom-cookie: YOUR_COOKIE_STRING' \
  -F 'file=@/path/to/your/image.jpg'

# 2. 使用返回的imageId进行识别
curl -X POST \
  'https://test-qwen-cor.aughumes8.workers.dev/recognize' \
  -H 'Content-Type: application/json' \
  -H 'x-custom-cookie: YOUR_COOKIE_STRING' \
  -d '{
    "imageId": "RETURNED_IMAGE_ID"
  }'
```
## Cloudflare访问数据
![image](https://github.com/user-attachments/assets/bb456075-6107-47ee-a361-a0edba532c38)
## 致谢
![image](https://github.com/user-attachments/assets/cfc04290-6400-483d-b0a9-4dd4b409bab9)
## 趋势
[![Star History Chart](https://api.star-history.com/svg?repos=cunninger/ocr-based-qwen&type=Date)](https://star-history.com/#Cunninger/ocr-based-qwen&Date)
