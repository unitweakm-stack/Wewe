# Telegram OCR Botni Render.com da Deploy Qilish Qo'llanmasi

Ushbu bot Render platformasida 24/7 ishlashi uchun maxsus Flask serveri bilan jihozlangan. Quyidagi qadamlarni bajaring:

## 1. Tayyorgarlik
1. [GitHub](https://github.com) hisobingizga kiring va yangi repository yarating.
2. Ushbu loyiha fayllarini (zip ichidagi `telegram_ocr_bot` papkasi tarkibini) GitHub repository-ga yuklang.

## 2. Render.com da Sozlash
1. [Render.com](https://render.com) saytida ro'yxatdan o'ting va GitHub hisobingizni ulang.
2. **New +** tugmasini bosing va **Web Service** ni tanlang.
3. GitHub-dagi repository-ni tanlang.
4. Quyidagi sozlamalarni kiriting:
   - **Name:** `telegram-ocr-bot`
   - **Environment:** `Python 3`
   - **Build Command:** `pip install -r requirements.txt`
   - **Start Command:** `python main.py`

## 3. Environment Variables (Muhit O'zgaruvchilari)
**Environment** bo'limiga o'ting va quyidagi o'zgaruvchilarni qo'shing:
- `TELEGRAM_BOT_TOKEN`: BotFather-dan olingan token.
- `OCR_SPACE_API_KEY`: [ocr.space](https://ocr.space/ocrapi) saytidan olingan bepul API kaliti.
- `PORT`: `8080` (Render buni avtomatik ham berishi mumkin).

## 4. 24/7 Ishlashini Ta'minlash (Uxlashni Oldini Olish)
Render-ning bepul rejasi (Free Tier) 15 daqiqa harakatsizlikdan so'ng "uxlab" qoladi. Buning oldini olish uchun:
1. [Cron-job.org](https://cron-job.org) kabi bepul servisdan foydalaning.
2. Render-dagi Web Service URL-ingizni (masalan: `https://telegram-ocr-bot.onrender.com/`) har 10-14 daqiqada bir marta "ping" qilib turadigan qilib sozlang.

## Muhim Eslatma
Bot foydalanuvchi obunalarini `user_subscriptions.json` faylida saqlaydi. Render-ning bepul rejasida fayllar har safar deploy bo'lganda o'chib ketadi. Agar ma'lumotlar saqlanib qolishini istasangiz, Render-da **Disk** (pullik) qo'shishingiz yoki ma'lumotlar bazasidan (masalan, MongoDB yoki PostgreSQL) foydalanish uchun kodni o'zgartirishingiz kerak bo'ladi.
