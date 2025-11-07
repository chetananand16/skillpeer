<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SkillSwap - Peer-to-Peer Learning</title>
    <!-- 1. Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- 2. Lucide Icons -->
    <script src="https://unpkg.com/lucide@latest"></script>
    <!-- 3. Inter Font -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">

    <style>
        /* Custom Styles */
        body {
            font-family: 'Inter', sans-serif;
        }
        /* A class to hide elements */
        .hidden {
            display: none;
        }
        /* Custom scrollbar for chat */
        .chat-window::-webkit-scrollbar {
            width: 6px;
        }
        .chat-window::-webkit-scrollbar-thumb {
            background-color: #9ca3af; /* gray-400 */
            border-radius: 3px;
        }
        .chat-window::-webkit-scrollbar-track {
            background-color: #e5e7eb; /* gray-200 */
        }
    </style>
</head>
<body class="bg-gray-50 text-gray-900 antialiased">

    <!-- Main Application Container -->
    <div class="min-h-screen">

        <!-- Header -->
        <header class="bg-white shadow-sm border-b border-gray-200">
            <nav class="container mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
                <div class="flex justify-between items-center h-16">
                    <!-- Logo -->
                    <div class="flex-shrink-0 flex items-center">
                        <svg class="w-8 h-8 text-indigo-600" width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" stroke="currentColor"><path d="M12 22a10 10 0 1 1 0-20 10 10 0 0 1 0 20Zm0-12v4m0 4h.01M12 6h.01"/></svg>
                        <span class="ml-2 text-2xl font-bold text-indigo-600">SkillSwap</span>
                    </div>
                    <!-- Nav Links -->
                    <div class="hidden md:flex md:items-center md:space-x-8">
                        <a href="#how-it-works" class="text-gray-600 hover:text-indigo-600 px-3 py-2 rounded-md text-sm font-medium">How It Works</a>
                        <a href="#" class="text-gray-600 hover:text-indigo-600 px-3 py-2 rounded-md text-sm font-medium">Browse Skills</a>
                        <button onclick="showPage('onboarding-page')" class="text-gray-600 hover:text-indigo-600 px-3 py-2 rounded-md text-sm font-medium">Log In</button>
                        <button onclick="showPage('onboarding-page')" class="ml-4 inline-flex items-center justify-center px-4 py-2 border border-transparent rounded-md shadow-sm text-sm font-medium text-white bg-indigo-600 hover:bg-indigo-700">
                            Get Started
                        </button>
                    </div>
                    <!-- Mobile Menu Button -->
                    <div class="md:hidden">
                        <button class="text-gray-500 hover:text-gray-700">
                            <i data-lucide="menu" class="w-6 h-6"></i>
                        </button>
                    </div>
                </div>
            </nav>
        </header>

        <!-- =================================================================== -->
        <!-- PAGE 1: LANDING PAGE                                                -->
        <!-- =================================================================== -->
        <main id="landing-page" class="page-content">
            <!-- Hero Section -->
            <div class="relative bg-white overflow-hidden">
                <div class="container mx-auto max-w-7xl">
                    <div class="relative z-10 pb-8 bg-white sm:pb-16 md:pb-20 lg:max-w-2xl lg:w-full lg:pb-28 xl:pb-32">
                        <main class="mt-10 mx-auto max-w-7xl px-4 sm:mt-12 sm:px-6 md:mt-16 lg:mt-20 lg:px-8 xl:mt-28">
                            <div class="sm:text-center lg:text-left">
                                <h1 class="text-4xl tracking-tight font-extrabold text-gray-900 sm:text-5xl md:text-6xl">
                                    <span class="block xl:inline">Teach what you know.</span>
                                    <span class="block text-indigo-600 xl:inline">Learn what you don't.</span>
                                </h1>
                                <p class="mt-3 text-base text-gray-600 sm:mt-5 sm:text-lg sm:max-w-xl sm:mx-auto md:mt-5 md:text-xl lg:mx-0">
                                    The global peer-to-peer skill exchange. Forget expensive courses and awkward forums. Find a partner and exchange expertise, one-on-one.
                                </p>
                                <div class="mt-5 sm:mt-8 sm:flex sm:justify-center lg:justify-start">
                                    <div class="rounded-md shadow">
                                        <button onclick="showPage('onboarding-page')" class="w-full flex items-center justify-center px-8 py-3 border border-transparent text-base font-medium rounded-md text-white bg-indigo-600 hover:bg-indigo-700 md:py-4 md:text-lg md:px-10">
                                            Get Started
                                        </button>
                                    </div>
                                    <div class="mt-3 sm:mt-0 sm:ml-3">
                                        <a href="#how-it-works" class="w-full flex items-center justify-center px-8 py-3 border border-transparent text-base font-medium rounded-md text-indigo-700 bg-indigo-100 hover:bg-indigo-200 md:py-4 md:text-lg md:px-10">
                                            How It Works
                                        </a>
                                    </div>
                                </div>
                            </div>
                        </main>
                    </div>
                </div>
                <div class="lg:absolute lg:inset-y-0 lg:right-0 lg:w-1/2">
                    <img class="h-56 w-full object-cover sm:h-72 md:h-96 lg:w-full lg:h-full" src="https://images.unsplash.com/photo-1552664730-d307ca884978?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1740&q=80" alt="Team collaborating">
                </div>
            </div>

            <!-- "How It Works" Section -->
            <section id="how-it-works" class="py-20 bg-gray-50">
                <div class="container mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
                    <div class="text-center">
                        <h2 class="text-base text-indigo-600 font-semibold tracking-wide uppercase">How It Works</h2>
                        <p class="mt-2 text-3xl font-extrabold text-gray-900 sm:text-4xl">
                            A new way to learn and grow.
                        </p>
                    </div>
                    <div class="mt-16 grid gap-10 md:grid-cols-2 lg:grid-cols-4">
                        <!-- Step 1 -->
                        <div class="flex flex-col items-center text-center p-6 bg-white rounded-lg shadow-lg">
                            <div class="flex items-center justify-center h-12 w-12 rounded-md bg-indigo-500 text-white">
                                <i data-lucide="user-plus"></i>
                            </div>
                            <h3 class="mt-5 text-xl font-bold text-gray-900">1. Offer & Want Profile</h3>
                            <p class="mt-2 text-base text-gray-600">
                                Tell us one skill you've mastered (your "Offer") and one skill you want to learn (your "Want").
                            </p>
                        </div>
                        <!-- Step 2 -->
                        <div class="flex flex-col items-center text-center p-6 bg-white rounded-lg shadow-lg">
                            <div class="flex items-center justify-center h-12 w-12 rounded-md bg-indigo-500 text-white">
                                <i data-lucide="users-round"></i>
                            </div>
                            <h3 class="mt-5 text-xl font-bold text-gray-900">2. Get "Perfect Match"</h3>
                            <p class="mt-2 text-base text-gray-600">
                                Our backend finds a user who wants to learn your skill and can teach you their skill.
                            </p>
                        </div>
                        <!-- Step 3 -->
                        <div class="flex flex-col items-center text-center p-6 bg-white rounded-lg shadow-lg">
                            <div class="flex items-center justify-center h-12 w-12 rounded-md bg-indigo-500 text-white">
                                <i data-lucide="layout-dashboard"></i>
                            </div>
                            <h3 class="mt-5 text-xl font-bold text-gray-900">3. In-Platform Classroom</h3>
                            <p class="mt-2 text-base text-gray-600">
                                Accept the match and join a shared workspace with video, chat, and a collaborative whiteboard.
                            </p>
                        </div>
                        <!-- Step 4 -->
                        <div class="flex flex-col items-center text-center p-6 bg-white rounded-lg shadow-lg">
                            <div class="flex items-center justify-center h-12 w-12 rounded-md bg-indigo-500 text-white">
                                <i data-lucide="star"></i>
                            </div>
                            <h3 class="mt-5 text-xl font-bold text-gray-900">4. Build "Trust Score"</h3>
                            <p class="mt-2 text-base text-gray-600">
                                After the session, partners must mutually review the exchange to build their reputation.
                            </p>
                        </div>
                    </div>
                </div>
            </section>
        </main>

        <!-- =================================================================== -->
        <!-- PAGE 2: ONBOARDING ("Offer & Want" Profile)                       -->
        <!-- =================================================================== -->
        <main id="onboarding-page" class="page-content hidden">
            <div class="min-h-[80vh] flex items-center justify-center py-12 px-4 sm:px-6 lg:px-8">
                <div class="max-w-md w-full space-y-8 bg-white p-10 rounded-xl shadow-lg">
                    <div>
                        <h2 class="mt-6 text-center text-3xl font-extrabold text-gray-900">
                            Create your Skill Profile
                        </h2>
                        <p class="mt-2 text-center text-sm text-gray-600">
                            What can you teach? What do you want to learn?
                        </p>
                    </div>
                    <form class="mt-8 space-y-6" action="#" method="POST" onsubmit="event.preventDefault(); findMatch();">
                        <div class="rounded-md shadow-sm -space-y-px">
                            <div>
                                <label for="skill-offer" class="block text-sm font-medium text-gray-700 mb-1">Skill I Master (Offer)</label>
                                <input id="skill-offer" name="skill-offer" type="text" required class="appearance-none rounded-md relative block w-full px-3 py-3 border border-gray-300 placeholder-gray-500 text-gray-900 focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm" placeholder="e.g., Advanced Excel Modeling" value="Advanced Excel Modeling">
                            </div>
                            <div class="pt-4">
                                <label for="skill-want" class="block text-sm font-medium text-gray-700 mb-1">Skill I Want (Learn)</label>
                                <input id="skill-want" name="skill-want" type="text" required class="appearance-none rounded-md relative block w-full px-3 py-3 border border-gray-300 placeholder-gray-500 text-gray-900 focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm" placeholder="e.g., Beginner Python for Data" value="Beginner Python for Data">
                            </div>
                        </div>

                        <div>
                            <button type="submit" class="group relative w-full flex justify-center py-3 px-4 border border-transparent text-sm font-medium rounded-md text-white bg-indigo-600 hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500">
                                Find My Perfect Match
                            </button>
                        </div>
                    </form>
                </div>
            </div>
        </main>

        <!-- =================================================================== -->
        <!-- PAGE 3: DASHBOARD (Matching Engine)                               -->
        <!-- =================================================================== -->
        <main id="dashboard-page" class="page-content hidden">
            <div class="container mx-auto max-w-4xl py-16 px-4">
                <h2 class="text-3xl font-extrabold text-gray-900 text-center mb-12">
                    Your Skill Dashboard
                </h2>

                <!-- Match Finder -->
                <div id="loading-match" class="hidden text-center p-10 bg-white rounded-lg shadow-lg">
                    <div class="flex justify-center items-center mb-4">
                        <svg class="animate-spin -ml-1 mr-3 h-8 w-8 text-indigo-600" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24">
                            <circle class="opacity-25" cx="12" cy="12" r="10" stroke="currentColor" stroke-width="4"></circle>
                            <path class="opacity-75" fill="currentColor" d="M4 12a8 8 0 018-8V0C5.373 0 0 5.373 0 12h4zm2 5.291A7.962 7.962 0 014 12H0c0 3.042 1.135 5.824 3 7.938l3-2.647z"></path>
                        </svg>
                    </div>
                    <p class="text-xl font-medium text-gray-700">Searching for your "Perfect Match"...</p>
                    <p class="text-gray-500">Scanning users who want <span class="font-bold text-gray-800" id="loading-offer"></span> and can teach <span class="font-bold text-gray-800" id="loading-want"></span>.</p>
                </div>

                <!-- Match Found -->
                <div id="match-found" class="hidden bg-white rounded-lg shadow-xl overflow-hidden">
                    <div class="p-8">
                        <div class="text-center">
                            <span class="inline-flex rounded-full bg-green-100 p-3">
                                <i data-lucide="check" class="w-8 h-8 text-green-700"></i>
                            </span>
                            <h3 class="mt-4 text-2xl font-bold text-gray-900">We found a "Perfect Match"!</h3>
                        </div>

                        <div class="mt-8 grid grid-cols-1 md:grid-cols-3 gap-6 border-t border-b border-gray-200 py-6">
                            <!-- Your Profile -->
                            <div class="text-center md:text-right">
                                <img class="w-16 h-16 rounded-full mx-auto md:mr-0 md:ml-auto" src="https://placehold.co/100x100/E0E7FF/4F46E5?text=You" alt="Your Profile">
                                <h4 class="mt-2 text-lg font-semibold">You</h4>
                            </div>
                            
                            <!-- The Exchange -->
                            <div class="flex flex-col items-center justify-center space-y-4">
                                <div class="text-center">
                                    <p class="text-sm text-gray-500">You Offer</p>
                                    <p class="font-semibold text-indigo-600" id="match-offer"></p>
                                </div>
                                <i data-lucide="arrow-right-left" class="text-gray-400 w-6 h-6"></i>
                                <div class="text-center">
                                    <p class="text-sm text-gray-500">You Want</p>
                                    <p class="font-semibold text-indigo-600" id="match-want"></p>
                                </div>
                            </div>

                            <!-- Match's Profile -->
                            <div class="text-center md:text-left">
                                <img class="w-16 h-16 rounded-full mx-auto md:ml-0 md:mr-auto" src="https://placehold.co/100x100/FEE2E2/B91C1C?text=SK" alt="Match's Profile">
                                <h4 class="mt-2 text-lg font-semibold">Sarah K.</h4>
                            </div>
                        </div>

                        <div class="mt-8 sm:flex sm:justify-center sm:space-x-4">
                            <button onclick="showPage('classroom-page')" type="button" class="w-full inline-flex justify-center rounded-md border border-transparent shadow-sm px-6 py-3 bg-indigo-600 text-base font-medium text-white hover:bg-indigo-700 sm:w-auto sm:text-sm">
                                Accept & Join Classroom
                            </button>
                            <button onclick="window.location.reload()" type="button" class="mt-3 w-full inline-flex justify-center rounded-md border border-gray-300 shadow-sm px-6 py-3 bg-white text-base font-medium text-gray-700 hover:bg-gray-50 sm:mt-0 sm:w-auto sm:text-sm">
                                Find a Different Match
                            </button>
                        </div>
                    </div>
                </div>
            </div>
        </main>

        <!-- =================================================================== -->
        <!-- PAGE 4: IN-PLATFORM CLASSROOM                                     -->
        <!-- =================================================================== -->
        <main id="classroom-page" class="page-content hidden">
            <!-- Classroom Header -->
            <div class="bg-gray-800 text-white">
                <div class="container mx-auto max-w-full px-4 sm:px-6 lg:px-8">
                    <div class="flex justify-between items-center h-16">
                        <div class="flex items-center">
                            <span class="relative flex h-3 w-3">
                                <span class="animate-ping absolute inline-flex h-full w-full rounded-full bg-red-400 opacity-75"></span>
                                <span class="relative inline-flex rounded-full h-3 w-3 bg-red-500"></span>
                            </span>
                            <span class="ml-3 text-lg font-medium">LIVE SESSION:</span>
                            <span class="ml-2 text-lg text-gray-300">Advanced Excel &lt;--&gt; Beginner Python</span>
                        </div>
                        <div class="flex items-center space-x-4">
                            <div class="flex items-center">
                                <i data-lucide="clock" class="w-5 h-5 text-gray-400"></i>
                                <span id="session-timer" class="ml-2 font-mono">00:00</span>
                            </div>
                            <button onclick="showPage('rating-modal')" class="inline-flex items-center px-4 py-2 border border-transparent rounded-md shadow-sm text-sm font-medium text-white bg-red-600 hover:bg-red-700">
                                <i data-lucide="phone-off" class="w-5 h-5 -ml-1 mr-2"></i>
                                End Session
                            </button>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Classroom Grid -->
            <div class="h-[calc(100vh-64px)] grid grid-cols-1 lg:grid-cols-4">
                
                <!-- Main Content Area (Video + Whiteboard) -->
                <div class="lg:col-span-3 bg-gray-100 p-4 grid grid-rows-2 gap-4">
                    
                    <!-- Video/Audio Call Area -->
                    <div class="row-span-1 bg-white rounded-lg shadow-md overflow-hidden p-4">
                        <h3 class="text-lg font-semibold text-gray-900 mb-3">Live Video/Audio Call</h3>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-4 h-[calc(100%-40px)]">
                            <!-- User 1 Video -->
                            <div class="relative bg-gray-900 rounded-lg flex items-center justify-center">
                                <img src="https://placehold.co/600x400/E0E7FF/4F46E5?text=Your+Video" class="object-cover h-full w-full rounded-lg">
                                <div class="absolute bottom-4 left-4 bg-black bg-opacity-50 text-white text-sm px-3 py-1 rounded-full">You (Teaching Excel)</div>
                                <div class="absolute top-4 right-4 flex space-x-2">
                                    <button class="p-2 bg-white bg-opacity-20 rounded-full text-white hover:bg-opacity-40"><i data-lucide="mic"></i></button>
                                    <button class="p-2 bg-white bg-opacity-20 rounded-full text-white hover:bg-opacity-40"><i data-lucide="video"></i></button>
                                </div>
                            </div>
                            <!-- User 2 Video -->
                            <div class="relative bg-gray-900 rounded-lg flex items-center justify-center">
                                <img src="https://placehold.co/600x400/FEE2E2/B91C1C?text=Sarah's+Video" class="object-cover h-full w-full rounded-lg">
                                <div class="absolute bottom-4 left-4 bg-black bg-opacity-50 text-white text-sm px-3 py-1 rounded-full">Sarah K. (Teaching Python)</div>
                                <div class="absolute top-4 right-4 flex space-x-2">
                                    <button class="p-2 bg-white bg-opacity-70 rounded-full text-gray-800"><i data-lucide="mic-off"></i></button>
                                    <button class="p-2 bg-white bg-opacity-20 rounded-full text-white hover:bg-opacity-40"><i data-lucide="video"></i></button>
                                </div>
                            </div>
                        </div>
                    </div>

                    <!-- Collaborative Whiteboard Area -->
                    <div class="row-span-1 bg-white rounded-lg shadow-md overflow-hidden flex flex-col">
                        <h3 class="text-lg font-semibold text-gray-900 p-4 border-b border-gray-200">Collaborative Whiteboard / Code Snippets</h3>
                        <div class="flex-1 p-4">
                            <textarea id="whiteboard" class="w-full h-full p-3 border border-gray-300 rounded-md resize-none font-mono text-sm focus:ring-indigo-500 focus:border-indigo-500" placeholder="Type your code snippets or diagrams here. Both users will see this text live."></textarea>
                        </div>
                    </div>

                </div>

                <!-- Side Panel (Persistent Chat) -->
                <div class="lg:col-span-1 bg-white border-l border-gray-200 flex flex-col h-full">
                    <h3 class="text-lg font-semibold text-gray-900 p-4 border-b border-gray-200">
                        Persistent Chat
                    </h3>
                    
                    <!-- Chat Window -->
                    <div id="chat-window" class="chat-window flex-1 p-4 space-y-4 overflow-y-auto">
                        <!-- Chat Message (Receiver) -->
                        <div class="flex">
                            <div class="flex-shrink-0 mr-3">
                                <img class="w-8 h-8 rounded-full" src="https://placehold.co/100x100/FEE2E2/B91C1C?text=SK" alt="Sarah K.">
                            </div>
                            <div>
                                <div class="bg-gray-100 text-gray-800 p-3 rounded-r-lg rounded-bl-lg">
                                    <p class="text-sm">Hey! Ready to start? I'm excited to learn about Excel pivot tables.</p>
                                </div>
                                <span class="text-xs text-gray-500 mt-1">Sarah K. - 10:30 AM</span>
                            </div>
                        </div>
                        <!-- Chat Message (Sender) -->
                        <div class="flex justify-end">
                            <div>
                                <div class="bg-indigo-600 text-white p-3 rounded-l-lg rounded-br-lg">
                                    <p class="text-sm">Absolutely! Let's start with your Python question first if you like? Can you show me a basic 'for loop'?</p>
                                </div>
                                <span class="text-xs text-gray-500 mt-1 flex justify-end">You - 10:31 AM</span>
                            </div>
                            <div class="flex-shrink-0 ml-3">
                                <img class="w-8 h-8 rounded-full" src="https://placehold.co/100x100/E0E7FF/4F46E5?text=You" alt="You">
                            </div>
                        </div>
                        <!-- More messages will be added by JS -->
                    </div>

                    <!-- Chat Input -->
                    <div class="p-4 border-t border-gray-200 bg-gray-50">
                        <form class="flex space-x-3" onsubmit="event.preventDefault(); sendChatMessage();">
                            <input id="chat-input" type="text" class="flex-1 block w-full px-4 py-2 border border-gray-300 rounded-full shadow-sm placeholder-gray-500 focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm" placeholder="Type a message...">
                            <button type="submit" class="inline-flex items-center justify-center w-10 h-10 rounded-full bg-indigo-600 text-white hover:bg-indigo-700">
                                <i data-lucide="send-horizontal" class="w-5 h-5"></i>
                            </button>
                        </form>
                    </div>
                </div>

            </div>
        </main>

        <!-- =================================================================== -->
        <!-- MODAL: "Trust Score" System (Rating & Review)                   -->
        <!-- =================================================================== -->
        <div id="rating-modal" class="page-content hidden">
            <div class="fixed z-50 inset-0 overflow-y-auto">
                <div class="flex items-center justify-center min-h-screen pt-4 px-4 pb-20 text-center sm:block sm:p-0">
                    
                    <!-- Background overlay -->
                    <div class="fixed inset-0 bg-gray-500 bg-opacity-75 transition-opacity" aria-hidden="true"></div>
                    
                    <!-- This element is to trick the browser into centering the modal contents. -->
                    <span class="hidden sm:inline-block sm:align-middle sm:h-screen" aria-hidden="true">&#8203;</span>
                    
                    <!-- Modal panel -->
                    <div class="inline-block align-bottom bg-white rounded-lg text-left overflow-hidden shadow-xl transform transition-all sm:my-8 sm:align-middle sm:max-w-lg sm:w-full">
                        <div class="bg-white px-4 pt-5 pb-4 sm:p-6 sm:pb-4">
                            <div class="sm:flex sm:items-start">
                                <div class="mx-auto flex-shrink-0 flex items-center justify-center h-12 w-12 rounded-full bg-green-100 sm:mx-0 sm:h-10 sm:w-10">
                                    <i data-lucide="star" class="h-6 w-6 text-green-600"></i>
                                </div>
                                <div class="mt-3 text-center sm:mt-0 sm:ml-4 sm:text-left">
                                    <h3 class="text-2xl leading-6 font-bold text-gray-900" id="modal-title">
                                        Session Complete!
                                    </h3>
                                    <div class="mt-4">
                                        <p class="text-base text-gray-600">
                                            Please review your exchange with <strong>Sarah K.</strong> to build your mutual Trust Score.
                                        </p>
                                    </div>

                                    <!-- Rating -->
                                    <div class="mt-6">
                                        <label class="block text-sm font-medium text-gray-700">How effective was the exchange?</label>
                                        <div class="mt-2 flex items-center space-x-1" id="star-rating">
                                            <i data-lucide="star" class="w-8 h-8 text-gray-300 hover:text-yellow-400 cursor-pointer" onclick="setRating(1)"></i>
                                            <i data-lucide="star" class="w-8 h-8 text-gray-300 hover:text-yellow-400 cursor-pointer" onclick="setRating(2)"></i>
                                            <i data-lucide="star" class="w-8 h-8 text-gray-300 hover:text-yellow-400 cursor-pointer" onclick="setRating(3)"></i>
                                            <i data-lucide="star" class="w-8 h-8 text-gray-300 hover:text-yellow-400 cursor-pointer" onclick="setRating(4)"></i>
                                            <i data-lucide="star" class="w-8 h-8 text-gray-300 hover:text-yellow-400 cursor-pointer" onclick="setRating(5)"></i>
                                        </div>
                                        <input type="hidden" id="rating-value" value="0">
                                    </div>

                                    <!-- Review -->
                                    <div class="mt-6">
                                        <label for="review" class="block text-sm font-medium text-gray-700">Write a brief review (required)</label>
                                        <div class="mt-1">
                                            <textarea rows="4" name="review" id="review" class="shadow-sm focus:ring-indigo-500 focus:border-indigo-500 block w-full sm:text-sm border border-gray-300 rounded-md p-2" placeholder="e.g., 'Sarah was a great teacher! She explained Python loops clearly and was a quick learner with Excel.'"></textarea>
                                        </div>
                                    </div>

                                </div>
                            </div>
                        </div>
                        <div class="bg-gray-50 px-4 py-3 sm:px-6 sm:flex sm:flex-row-reverse">
                            <button onclick="submitReview()" type="button" class="w-full inline-flex justify-center rounded-md border border-transparent shadow-sm px-4 py-2 bg-indigo-600 text-base font-medium text-white hover:bg-indigo-700 sm:ml-3 sm:w-auto sm:text-sm">
                                Submit Review & Exit
                            </button>
                            <button onclick="showPage('dashboard-page')" type="button" class="mt-3 w-full inline-flex justify-center rounded-md border border-gray-300 shadow-sm px-4 py-2 bg-white text-base font-medium text-gray-700 hover:bg-gray-50 sm:mt-0 sm:w-auto sm:text-sm">
                                Skip
                            </button>
                        </div>
                    </div>
                </div>
            </div>
        </div>


    </div> <!-- End Main Application Container -->

    <!-- =================================================================== -->
    <!-- JAVASCRIPT LOGIC                                                    -->
    <!-- =================================================================== -->
    <script>
        // --- Icon Initialization ---
        lucide.createIcons();

        // --- Page Navigation ---
        const pages = document.querySelectorAll('.page-content');
        let currentRating = 0;
        let sessionTimerInterval;
        let sessionSeconds = 0;

        function showPage(pageId) {
            // Hide all pages
            pages.forEach(page => {
                page.classList.add('hidden');
            });

            // Show the target page
            const targetPage = document.getElementById(pageId);
            if (targetPage) {
                targetPage.classList.remove('hidden');
            } else {
                console.error('Page not found:', pageId);
                document.getElementById('landing-page').classList.remove('hidden'); // Fallback
            }

            // Scroll to top
            window.scrollTo(0, 0);

            // Page-specific logic
            if (pageId === 'classroom-page') {
                startSessionTimer();
            } else {
                stopSessionTimer();
            }

            if (pageId === 'rating-modal') {
                resetRating();
            }
        }

        // --- Onboarding & Matching Logic ---
        function findMatch() {
            const offerSkill = document.getElementById('skill-offer').value;
            const wantSkill = document.getElementById('skill-want').value;

            // 1. Show dashboard
            showPage('dashboard-page');
            
            // 2. Show loading spinner
            document.getElementById('loading-match').classList.remove('hidden');
            document.getElementById('match-found').classList.add('hidden');
            document.getElementById('loading-offer').textContent = wantSkill; // We are looking for someone who WANTS what you OFFER
            document.getElementById('loading-want').textContent = offerSkill; // and OFFERS what you WANT

            // 3. Simulate backend matching delay
            setTimeout(() => {
                // 4. Hide loading and show match
                document.getElementById('loading-match').classList.add('hidden');
                document.getElementById('match-found').classList.remove('hidden');
                
                // 5. Populate match card
                document.getElementById('match-offer').textContent = offerSkill;
                document.getElementById('match-want').textContent = wantSkill;

            }, 2500); // 2.5 second delay
        }

        // --- Classroom Logic ---

        // Session Timer
        function startSessionTimer() {
            if (sessionTimerInterval) return; // Already running
            sessionSeconds = 0;
            const timerElement = document.getElementById('session-timer');
            
            sessionTimerInterval = setInterval(() => {
                sessionSeconds++;
                const minutes = Math.floor(sessionSeconds / 60).toString().padStart(2, '0');
                const seconds = (sessionSeconds % 60).toString().padStart(2, '0');
                timerElement.textContent = `${minutes}:${seconds}`;
            }, 1000);
        }

        function stopSessionTimer() {
            clearInterval(sessionTimerInterval);
            sessionTimerInterval = null;
        }

        // Simulated Chat
        function sendChatMessage() {
            const input = document.getElementById('chat-input');
            const message = input.value.trim();
            if (message === '') return;

            const chatWindow = document.getElementById('chat-window');

            // Create and append sender's message
            const senderMessage = document.createElement('div');
            senderMessage.className = 'flex justify-end';
            senderMessage.innerHTML = `
                <div>
                    <div class="bg-indigo-600 text-white p-3 rounded-l-lg rounded-br-lg">
                        <p class="text-sm">${message}</p>
                    </div>
                    <span class="text-xs text-gray-500 mt-1 flex justify-end">You - (Now)</span>
                </div>
                <div class="flex-shrink-0 ml-3">
                    <img class="w-8 h-8 rounded-full" src="https://placehold.co/100x100/E0E7FF/4F46E5?text=You" alt="You">
                </div>
            `;
            chatWindow.appendChild(senderMessage);
            
            // Clear input
            input.value = '';
            // Scroll to bottom
            chatWindow.scrollTop = chatWindow.scrollHeight;

            // Simulate a reply
            setTimeout(() => {
                const receiverMessage = document.createElement('div');
                receiverMessage.className = 'flex';
                receiverMessage.innerHTML = `
                    <div class="flex-shrink-0 mr-3">
                        <img class="w-8 h-8 rounded-full" src="https://placehold.co/100x100/FEE2E2/B91C1C?text=SK" alt="Sarah K.">
                    </div>
                    <div>
                        <div class="bg-gray-100 text-gray-800 p-3 rounded-r-lg rounded-bl-lg">
                            <p class="text-sm">Got it, thanks! Let me try that on the whiteboard.</p>
                        </div>
                        <span class="text-xs text-gray-500 mt-1">Sarah K. - (Now)</span>
                    </div>
                `;
                chatWindow.appendChild(receiverMessage);
                chatWindow.scrollTop = chatWindow.scrollHeight;
            }, 1500);
        }

        // --- Rating Modal Logic ---
        function setRating(stars) {
            currentRating = stars;
            document.getElementById('rating-value').value = stars;
            const starIcons = document.querySelectorAll('#star-rating i');
            
            starIcons.forEach((star, index) => {
                if (index < stars) {
                    star.classList.remove('text-gray-300');
                    star.classList.add('text-yellow-400');
                    star.setAttribute('fill', 'currentColor');
                } else {
                    star.classList.add('text-gray-300');
                    star.classList.remove('text-yellow-400');
                    star.setAttribute('fill', 'none');
                }
            });
            // Re-run lucide to update fill
            lucide.createIcons();
        }

        function resetRating() {
            setRating(0);
            document.getElementById('review').value = '';
        }

        function submitReview() {
            const reviewText = document.getElementById('review').value;
            if (currentRating === 0 || reviewText.trim() === '') {
                alert('Please select a rating and write a review before submitting.');
                return;
            }
            
            console.log('Rating:', currentRating);
            console.log('Review:', reviewText);
            
            // Hide modal and show dashboard
            alert('Thank you for your review! Your Trust Score has been updated.'); // Using alert here for demo
            showPage('dashboard-page');
            document.getElementById('match-found').classList.add('hidden'); // Hide the old match
        }


        // --- Initial Page Load ---
        // Ensure landing page is shown by default (even on refresh)
        showPage('landing-page');

    </script>
</body>
</html>
