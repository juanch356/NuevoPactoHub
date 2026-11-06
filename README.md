<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Nuevo Pacto Hub - SCV</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" rel="stylesheet">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap');
        body { font-family: 'Inter', sans-serif; background-color: #0f172a; color: #f8fafc; }
        .app-container { max-width: 480px; margin: 0 auto; min-height: 100vh; background: #1e293b; display: flex; flex-direction: column; position: relative; box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.7); }
    </style>
</head>
<body>
    <div class="app-container" id="app">
        <!-- Pantalla de Login / Bienvenida con tu Logo Oficial -->
        <div id="login-screen" class="flex flex-col items-center justify-center flex-1 p-6 text-center">
            <div class="mb-6">
                <!-- Tu logotipo oficial exacto integrado -->
                <img src="1538.jpg" alt="Iglesia Nuevo Pacto SCV Logo" class="w-44 h-44 rounded-full mx-auto object-cover border-4 border-amber-500 shadow-2xl mb-4" onerror="this.src='https://images.unsplash.com/photo-1544717305-2782549b5136?w=300&h=300&fit=crop'">
                <h1 class="text-2xl font-bold text-amber-400">Iglesia Nuevo Pacto SCV</h1>
                <p class="text-sm text-slate-400 mt-1">Plataforma Oficial de Administración y Comunidad</p>
            </div>
            
            <div class="w-full bg-slate-800/80 p-6 rounded-2xl border border-slate-700 shadow-xl">
                <h2 class="text-lg font-semibold mb-4 text-white">Iniciar Sesión Admin</h2>
                <div class="mb-4 text-left">
                    <label class="block text-xs font-medium text-slate-300 mb-1">Usuario</label>
                    <input type="text" id="login-user" value="juan.chinchilla" class="w-full bg-slate-900 border border-slate-700 rounded-xl px-4 py-3 text-sm text-white focus:outline-none focus:border-amber-500">
                </div>
                <div class="mb-6 text-left">
                    <label class="block text-xs font-medium text-slate-300 mb-1">Contraseña</label>
                    <input type="password" id="login-pass" value="admin123" class="w-full bg-slate-900 border border-slate-700 rounded-xl px-4 py-3 text-sm text-white focus:outline-none focus:border-amber-500">
                </div>
                <button onclick="handleLogin()" class="w-full bg-gradient-to-r from-amber-500 to-amber-600 hover:from-amber-600 hover:to-amber-700 text-slate-950 font-bold py-3 px-4 rounded-xl shadow-lg transition duration-200">
                    Abrir Aplicación
                </button>
            </div>
        </div>

        <!-- Panel Principal de Administrador -->
        <div id="main-app" class="hidden flex flex-col flex-1">
            <header class="bg-slate-900 border-b border-slate-800 p-4 flex items-center justify-between sticky top-0 z-50">
                <div class="flex items-center space-x-3">
                    <img src="1538.jpg" alt="Logo" class="w-10 h-10 rounded-full border border-amber-500 object-cover">
                    <div>
                        <h2 class="text-sm font-bold text-amber-400">Nuevo Pacto SCV</h2>
                        <p class="text-xs text-slate-400">Juan Chinchilla (Admin)</p>
                    </div>
                </div>
                <button onclick="handleLogout()" class="text-slate-400 hover:text-red-400 text-sm"><i class="fa-solid fa-right-from-bracket"></i> Salir</button>
            </header>

            <main class="flex-1 p-4 pb-20 overflow-y-auto">
                <div class="bg-slate-800 border border-slate-700 rounded-2xl p-5 text-center shadow-lg mb-4">
                    <i class="fa-solid fa-shield-halved text-4xl text-amber-500 mb-3"></i>
                    <h3 class="text-xl font-bold text-white mb-2">Panel de Administrador Activo</h3>
                    <p class="text-sm text-slate-300 mb-4">Acceso total autorizado para gestionar boletines, turnos y calendarios ministeriales.</p>
                </div>
                
                <div class="grid grid-cols-2 gap-3">
                    <div onclick="alert('Módulo de Boletines Activo')" class="bg-slate-800/80 border border-slate-700 p-4 rounded-xl text-center cursor-pointer hover:border-amber-500 transition">
                        <i class="fa-solid fa-newspaper text-amber-400 text-2xl mb-2"></i>
                        <h4 class="text-sm font-bold">Boletines</h4>
                    </div>
                    <div onclick="alert('Módulo de Calendario y Turnos Activo')" class="bg-slate-800/80 border border-slate-700 p-4 rounded-xl text-center cursor-pointer hover:border-amber-500 transition">
                        <i class="fa-solid fa-calendar-days text-amber-400 text-2xl mb-2"></i>
                        <h4 class="text-sm font-bold">Calendarios</h4>
                    </div>
                    <div onclick="alert('Módulo de Alabanza Activo')" class="bg-slate-800/80 border border-slate-700 p-4 rounded-xl text-center cursor-pointer hover:border-amber-500 transition">
                        <i class="fa-solid fa-music text-amber-400 text-2xl mb-2"></i>
                        <h4 class="text-sm font-bold">Alabanza</h4>
                    </div>
                    <div onclick="alert('Directorio de Miembros Activo')" class="bg-slate-800/80 border border-slate-700 p-4 rounded-xl text-center cursor-pointer hover:border-amber-500 transition">
                        <i class="fa-solid fa-users text-amber-400 text-2xl mb-2"></i>
                        <h4 class="text-sm font-bold">Miembros</h4>
                    </div>
                </div>
            </main>
        </div>
    </div>

    <script>
        function handleLogin() {
            const u = document.getElementById('login-user').value.trim().toLowerCase();
            const p = document.getElementById('login-pass').value.trim();
            if(u === 'juan.chinchilla' && p === 'admin123') {
                document.getElementById('login-screen').classList.add('hidden');
                document.getElementById('main-app').classList.remove('hidden');
            } else {
                alert('Credenciales incorrectas. Verifique usuario y contraseña de administrador.');
            }
        }
        function handleLogout() {
            document.getElementById('main-app').classList.add('hidden');
            document.getElementById('login-screen').classList.remove('hidden');
        }
    </script>
</body>
</html>
