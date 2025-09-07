<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>پنل ثبت IP برای DNS</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Vazirmatn:wght@400;500;700&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Vazirmatn', sans-serif;
            background-color: #1a202c; /* bg-gray-900 */
            color: #e2e8f0; /* text-gray-200 */
        }
        .form-input {
            background-color: #2d3748; /* bg-gray-800 */
            border-color: #4a5568; /* border-gray-600 */
            color: #e2e8f0; /* text-gray-200 */
            text-align: left;
            direction: ltr;
        }
        .form-input::placeholder {
            color: #718096; /* text-gray-400 */
        }
        .btn-primary {
            background-color: #4299e1; /* bg-blue-500 */
            transition: background-color: 0.3s;
        }
        .btn-primary:hover {
            background-color: #3182ce; /* bg-blue-600 */
        }
        .btn-primary:disabled {
            background-color: #4a5568; /* bg-gray-600 */
            cursor: not-allowed;
        }
        .toast {
            visibility: hidden;
            opacity: 0;
            transition: opacity 0.5s, visibility 0.5s;
        }
        .toast.show {
            visibility: visible;
            opacity: 1;
        }
    </style>
</head>
<body class="flex items-center justify-center min-h-screen">

    <div class="w-full max-w-md p-8 space-y-8 bg-gray-800 rounded-xl shadow-lg">
        <div>
            <h2 class="text-3xl font-bold text-center text-white">به‌روزرسانی IP</h2>
            <p class="mt-2 text-center text-sm text-gray-400">
                آدرس IP فعلی خود را برای سرویس DNS ثبت کنید.
            </p>
        </div>

        <div class="space-y-6">
            <div>
                <label for="username" class="text-sm font-medium text-gray-300">نام کاربری شما</label>
                <input id="username" name="username" type="text" required
                       class="form-input block w-full px-3 py-2 mt-1 border rounded-md shadow-sm focus:outline-none focus:ring-blue-500 focus:border-blue-500 sm:text-sm"
                       placeholder="نام کاربری که دریافت کرده‌اید">
            </div>

            <div>
                <button id="submitBtn" onclick="updateClientIp()"
                        class="btn-primary w-full flex justify-center py-2 px-4 border border-transparent rounded-md shadow-sm text-sm font-medium text-white focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-blue-500">
                    <span id="btnText">بررسی و ثبت IP</span>
                    <svg id="spinner" class="animate-spin -ml-1 mr-3 h-5 w-5 text-white hidden" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24">
                        <circle class="opacity-25" cx="12" cy="12" r="10" stroke="currentColor" stroke-width="4"></circle>
                        <path class="opacity-75" fill="currentColor" d="M4 12a8 8 0 018-8V0C5.373 0 0 5.373 0 12h4zm2 5.291A7.962 7.962 0 014 12H0c0 3.042 1.135 5.824 3 7.938l3-2.647z"></path>
                    </svg>
                </button>
            </div>
        </div>

        <!-- Toast Notification -->
        <div id="toast" class="toast fixed bottom-5 right-5 flex items-center w-full max-w-xs p-4 space-x-4 text-gray-500 bg-white divide-x divide-gray-200 rounded-lg shadow dark:text-gray-400 dark:divide-gray-700 space-x-reverse dark:bg-gray-800" role="alert">
            <div id="toast-icon" class="text-2xl"></div>
            <div id="toast-message" class="pr-4 text-sm font-normal"></div>
        </div>
    </div>

<script>
    // -------------------------------------------------------------------
    // !!! توجه: تنظیمات مهم - این بخش را با دقت ویرایش کنید !!!
    // -------------------------------------------------------------------

    // 1. آدرس کامل ورکر کلودفلر خود را اینجا وارد کنید.
    // مثال: "https://my-worker.my-account.workers.dev"
    const WORKER_URL = "https://your-worker-url.workers.dev";

    // -------------------------------------------------------------------
    
    const submitBtn = document.getElementById('submitBtn');
    const btnText = document.getElementById('btnText');
    const spinner = document.getElementById('spinner');

    function showToast(message, isSuccess) {
        const toast = document.getElementById('toast');
        const toastMessage = document.getElementById('toast-message');
        const toastIcon = document.getElementById('toast-icon');

        toastMessage.textContent = message;
        if (isSuccess) {
            toast.classList.remove('bg-red-200', 'dark:bg-red-800');
            toast.classList.add('bg-green-200', 'dark:bg-green-800');
            toastIcon.textContent = '✅';
        } else {
            toast.classList.remove('bg-green-200', 'dark:bg-green-800');
            toast.classList.add('bg-red-200', 'dark:bg-red-800');
            toastIcon.textContent = '❌';
        }
        
        toast.classList.add('show');
        setTimeout(() => {
            toast.classList.remove('show');
        }, 5000);
    }

    async function updateClientIp() {
        const username = document.getElementById('username').value.trim();
        if (!username) {
            showToast('لطفاً نام کاربری خود را وارد کنید.', false);
            return;
        }
        if (WORKER_URL === "https://your-worker-url.workers.dev") {
            showToast('خطای پیکربندی: لطفاً آدرس ورکر را در فایل HTML ویرایش کنید.', false);
            return;
        }

        // --- UI Loading State ---
        submitBtn.disabled = true;
        btnText.textContent = 'در حال پردازش...';
        spinner.classList.remove('hidden');

        try {
            const response = await fetch(WORKER_URL, {
                method: 'POST',
                headers: {
                    'Content-Type': 'application/json'
                },
                body: JSON.stringify({ username: username })
            });

            const result = await response.json();

            if (response.ok) {
                showToast(result.message, true);
            } else {
                throw new Error(result.error || 'یک خطای ناشناخته رخ داد.');
            }

        } catch (error) {
            console.error('An error occurred:', error);
            let errorMessage = 'یک خطای غیرمنتظره رخ داد.';
             if (error.message.includes('Failed to fetch')) {
                 errorMessage = 'خطای شبکه. آیا آدرس ورکر صحیح است و ورکر فعال است؟';
            } else {
                 errorMessage = error.message;
            }
            showToast(errorMessage, false);
        } finally {
            // --- UI Reset State ---
            submitBtn.disabled = false;
            btnText.textContent = 'بررسی و ثبت IP';
            spinner.classList.add('hidden');
        }
    }
</script>

</body>
</html>
