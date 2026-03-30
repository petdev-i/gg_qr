<!DOCTYPE html>
<html lang="th">

<head>
	<meta charset="UTF-8">
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	<title>ระบบถอดรหัสข้อมูล QR Code</title>

	<script src="https://cdnjs.cloudflare.com/ajax/libs/crypto-js/4.1.1/crypto-js.min.js"></script>
	<style>
		:root {
			--primary-color: #3498db;
			/* สีฟ้าหลัก */
			--bg-color: #f4f7f6;
			--card-color: #ffffff;
			--text-color: #2c3e50;
			--success-color: #27ae60;
			--error-color: #e74c3c;
		}

		body {
			font-family: 'Sarabun', sans-serif;
			/* ใช้ฟอนต์ไทยที่ดูทันสมัย */
			background-color: var(--bg-color);
			color: var(--text-color);
			margin: 0;
			display: flex;
			justify-content: center;
			align-items: center;
			height: 100vh;
		}

		.container {
			background-color: var(--card-color);
			padding: 2.5rem;
			border-radius: 15px;
			box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
			width: 90%;
			max-width: 500px;
			text-align: center;
		}

		h1 {
			color: var(--primary-color);
			font-size: 1.5rem;
			margin-bottom: 0.5rem;
		}

		p.subtitle {
			color: #7f8c8d;
			margin-bottom: 2rem;
		}

		.result-box {
			border: 2px solid #eee;
			border-radius: 10px;
			padding: 1.5rem;
			min-height: 50px;
			margin-top: 1rem;
			position: relative;
			background-color: #fafafa;
		}

		/* สถานะการทำงาน */
		.status {
			font-weight: bold;
			margin-bottom: 1rem;
		}

		.loading {
			color: var(--primary-color);
		}

		.success {
			color: var(--success-color);
		}

		.error {
			color: var(--error-color);
		}

		/* พื้นที่แสดงข้อมูลที่ถอดรหัสแล้ว */
		#original-data {
			font-size: 1.2rem;
			word-break: break-all;
			/* ป้องกันข้อความยาวเกินจอล้น */
			white-space: pre-wrap;
			/* รักษาการเว้นบรรทัด (ถ้ามี) */
		}

		/* อนิเมชั่นโหลดดิ้งพื้นฐาน */
		.spinner {
			border: 4px solid #f3f3f3;
			border-top: 4px solid var(--primary-color);
			border-radius: 50%;
			width: 30px;
			height: 30px;
			animation: spin 1s linear infinite;
			margin: 0 auto;
		}

		@keyframes spin {
			0% {
				transform: rotate(0deg);
			}

			100% {
				transform: rotate(360deg);
			}
		}

		.hidden {
			display: none;
		}
	</style>
</head>

<body>

	<div class="container">
		<h1>ระบบถอดรหัสข้อมูล QR Code</h1>
		<p class="subtitle">สแกนเพื่ออ่านข้อมูลอย่างปลอดภัย</p>

		<div id="loading-state" class="status loading">
			<div class="spinner"></div>
			<p>กำลังถอดรหัสข้อมูล...</p>
		</div>

		<div id="result-state" class="result-box hidden">
			<div class="status success">✓ ถอดรหัสสำเร็จ</div>
			<div id="original-data"></div>
		</div>

		<div id="error-state" class="result-box hidden">
			<div class="status error">⚠ เกิดข้อผิดพลาด</div>
			<div id="error-message">ไม่สามารถถอดรหัสได้<br>กุญแจไม่ถูกต้องหรือข้อมูลเสียหาย</div>
		</div>
	</div>

	<script>
		// ตรวจสอบว่า SECRET_KEY ใน JS ตรงกับที่ใส่ในสูตร Google Sheets หรือไม่
		const SECRET_KEY = "myPassword123"; // <--- ต้องเป๊ะทุกตัวอักษร!

		function decodeQRCodeData() {
			const urlParams = new URLSearchParams(window.location.search);
			let encryptedData = urlParams.get('data');
			const SECRET_KEY = "myPassword123"; // <--- ต้องตรงกับในช่อง B2

			if (encryptedData) {
				try {
					// 1. จัดการข้อมูลให้พร้อม
					encryptedData = decodeURIComponent(encryptedData).replace(/ /g, '+');

					// 2. สร้าง Key และ IV ชุดเดียวกับใน Google Sheets
					const keyHex = CryptoJS.SHA256(SECRET_KEY);
					const iv = CryptoJS.enc.Utf8.parse("1234567890123456");

					// 3. ถอดรหัส
					const bytes = CryptoJS.AES.decrypt(encryptedData, keyHex, {
						iv: iv,
						mode: CryptoJS.mode.CBC,
						padding: CryptoJS.pad.Pkcs7
					});

					const originalText = bytes.toString(CryptoJS.enc.Utf8);

					if (!originalText) throw new Error("Key ผิดหรือข้อมูลพัง");

					document.getElementById('original-data').innerText = originalText;
					document.getElementById('result-state').classList.remove('hidden');
					document.getElementById('loading-state').classList.add('hidden');

				} catch (error) {
					console.error("Decryption error:", error);
					document.getElementById('loading-state').classList.add('hidden');
					document.getElementById('error-state').classList.remove('hidden');
				}
			}
		}
	</script>

</body>

</html>