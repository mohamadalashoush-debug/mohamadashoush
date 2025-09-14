<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Modern Personal Page</title>
    <!-- Include Tailwind CSS from CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        /* Import a modern, clean font */
        @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;700;800&display=swap');
        body {
            font-family: 'Poppins', sans-serif;
            background-color: #f7f9fc;
        }
        .container {
            max-width: 800px;
        }
        .section-card {
            background-color: #ffffff;
            border-radius: 1rem;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            /* Initial state for animation */
            opacity: 0;
            transform: translateY(50px);
            transition: opacity 0.8s ease-out, transform 0.8s ease-out;
        }
        .section-card.is-visible {
            opacity: 1;
            transform: translateY(0);
        }
        .project-card {
            background-color: #f0f4f8;
            transition: all 0.3s ease-in-out;
            animation: fadeIn 0.8s ease-in-out;
        }
        .project-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 15px rgba(0, 0, 0, 0.1);
            cursor: pointer;
        }
        .highlight-text {
            color: #3b82f6;
        }
        .nav-link {
            color: #4b5563;
        }
        .nav-link:hover {
            color: #1f2937;
        }
        /* Custom animation for cards */
        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        .animate-delay-1 {
            animation-delay: 0.2s;
        }
        .animate-delay-2 {
            animation-delay: 0.4s;
        }
        .animate-delay-3 {
            animation-delay: 0.6s;
        }
        .animate-delay-4 {
            animation-delay: 0.8s;
        }
        .profile-container {
            position: relative;
            width: 200px;
            height: 200px;
            border-radius: 50%;
            overflow: hidden;
            display: flex;
            justify-content: center;
            align-items: center;
        }
        .profile-container:hover .profile-picture {
            transform: scale(1.05);
            box-shadow: 0 0 20px rgba(59, 130, 246, 0.8);
        }
        .profile-picture {
            width: 100%;
            height: 100%;
            object-fit: cover;
            border-radius: 50%;
            transition: transform 0.4s ease, box-shadow 0.4s ease;
            filter: grayscale(0.2);
        }
        .profile-picture:hover {
            filter: grayscale(0);
        }
        .creative-name {
            font-family: 'Poppins', sans-serif;
            font-weight: 800;
            text-transform: uppercase;
            letter-spacing: 2px;
            background: linear-gradient(45deg, #3b82f6, #60a5fa, #2563eb);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.1);
        }
        
        /* New styles for the background using a gradient for reliability */
        .header-background {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, #1e3a8a, #3b82f6);
            background-size: cover;
            background-position: center;
            z-index: -1;
            filter: brightness(0.9); /* Adjust brightness for text readability */
            transition: filter 0.5s ease;
        }

        .header-background:hover {
            filter: brightness(1.1);
        }

        /* Modal specific styles */
        .modal {
            display: none; /* Hidden by default */
            position: fixed;
            z-index: 100;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            overflow: auto;
            background-color: rgba(0, 0, 0, 0.7);
            backdrop-filter: blur(5px);
            -webkit-backdrop-filter: blur(5px);
            animation: fadeInModal 0.3s ease-in-out;
        }

        .modal-content {
            background-color: #fefefe;
            margin: 5% auto;
            padding: 2rem;
            border-radius: 1rem;
            max-width: 600px;
            position: relative;
            animation: slideIn 0.5s ease-out;
        }

        .close-button {
            position: absolute;
            top: 1rem;
            right: 1rem;
            color: #aaa;
            font-size: 2rem;
            font-weight: bold;
            cursor: pointer;
            transition: color 0.3s ease;
        }

        .close-button:hover,
        .close-button:focus {
            color: #000;
        }

        @keyframes fadeInModal {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        @keyframes slideIn {
            from { transform: translateY(-50px); opacity: 0; }
            to { transform: translateY(0); opacity: 1; }
        }
    </style>
</head>
<body class="text-gray-800 leading-relaxed">

    <!-- Navbar -->
    <nav class="sticky top-0 z-50 w-full bg-white bg-opacity-90 backdrop-blur-lg shadow-md">
        <div class="container mx-auto px-4 py-4 flex justify-center space-x-8">
            <a href="#about" class="text-lg nav-link transition-colors duration-300">About</a>
            <a href="#gallery" class="text-lg nav-link transition-colors duration-300">Gallery</a>
            <a href="#career" class="text-lg nav-link transition-colors duration-300">Career</a>
            <a href="#portfolio" class="text-lg nav-link transition-colors duration-300">Portfolio</a>
            <a href="#tools" class="text-lg nav-link transition-colors duration-300">Tools & Skills</a>
            <a href="#contact" class="text-lg nav-link transition-colors duration-300">Contact</a>
        </div>
    </nav>

    <div class="container mx-auto px-4 py-16 flex flex-col items-center">

        <!-- Header Section -->
        <header class="text-center mb-16 relative w-full h-80 overflow-hidden rounded-3xl">
            <!-- New Background Gradient for a professional look -->
            <div class="header-background"></div>
            <div class="relative z-10 flex flex-col items-center justify-center h-full">
                <!-- Logo Space -->
                <div class="mb-4">
                    <!-- If you have a logo, you can add it here. Example: -->
                    <!-- <img src="your-logo-url.png" alt="Your Logo" class="h-16 mx-auto"> -->
                </div>
                <!-- Profile Picture Section -->
                <div class="mb-8 relative profile-container mx-auto">
                    <img 
                        src="https://placehold.co/200x200/cccccc/ffffff?text=Your+Photo" 
                        alt="Your Profile Picture" 
                        class="profile-picture"
                    >
                </div>
                
                <h1 class="text-3xl md:text-4xl creative-name mb-2">
                    Mohamad AlAshoush
                </h1>
                <p class="text-lg md:text-xl text-white font-light mt-2">
                    Digital Marketing & Social Media Expert
                </p>
            </div>
        </header>

        <!-- About Section -->
        <section id="about" class="w-full section-card p-10 rounded-3xl shadow-lg mb-12">
            <h2 class="text-2xl font-bold highlight-text mb-4">
                About
            </h2>
            <p class="text-gray-600">
                A results-driven digital marketing expert with 7+ years of experience driving sales and brand growth for luxury brands in the UAE. Skilled in crafting and executing impactful social media campaigns, creating engaging content, and optimizing digital marketing efforts. I am passionate about bringing my experience and dedication to a forward-thinking company that is poised for customer-focused innovation and excellence.
            </p>
        </section>
        
        <!-- Gallery Section -->
        <section id="gallery" class="w-full section-card p-10 rounded-3xl shadow-lg mb-12">
            <h2 class="text-2xl font-bold highlight-text mb-8 text-center">
                Gallery
            </h2>
            <div class="grid grid-cols-2 md:grid-cols-3 gap-6">
                <!-- Image 1 -->
                <img src="https://placehold.co/400x300/e0e0e0/ffffff?text=Image+1" alt="Image 1" class="rounded-xl shadow-lg transform hover:scale-105 transition-transform duration-300">
                <!-- Image 2 -->
                <img src="https://placehold.co/400x300/d0d0d0/ffffff?text=Image+2" alt="Image 2" class="rounded-xl shadow-lg transform hover:scale-105 transition-transform duration-300">
                <!-- Image 3 -->
                <img src="https://placehold.co/400x300/c0c0c0/ffffff?text=Image+3" alt="Image 3" class="rounded-xl shadow-lg transform hover:scale-105 transition-transform duration-300">
                <!-- Image 4 -->
                <img src="https://placehold.co/400x300/b0b0b0/ffffff?text=Image+4" alt="Image 4" class="rounded-xl shadow-lg transform hover:scale-105 transition-transform duration-300">
                <!-- Image 5 -->
                <img src="https://placehold.co/400x300/a0a0a0/ffffff?text=Image+5" alt="Image 5" class="rounded-xl shadow-lg transform hover:scale-105 transition-transform duration-300">
                <!-- Image 6 -->
                <img src="https://placehold.co/400x300/909090/ffffff?text=Image+6" alt="Image 6" class="rounded-xl shadow-lg transform hover:scale-105 transition-transform duration-300">
            </div>
        </section>

        <!-- Career Section -->
        <section id="career" class="w-full section-card p-10 rounded-3xl shadow-lg mb-12">
            <h2 class="text-2xl font-bold highlight-text mb-4">
                Career
            </h2>
            <div class="space-y-6 text-gray-600">
                <p>
                    <strong>Digital Marketing & Social Media Officer</strong> <br>
                    DEC 2021 - Present at Alsheraifi Group – Dubai, UAE
                    <ul class="list-disc list-inside mt-2">
                        <li>Increased sales by +20% across three brands through data-driven social media campaigns.</li>
                        <li>Generated more than 24,000 leads via social media campaigns.</li>
                        <li>Managed and optimized Meta and Google Ads, leading to cost-effective lead generation.</li>
                    </ul>
                </p>
                <p>
                    <strong>Digital Marketing & Social Media Executive</strong> <br>
                    JUL 2018 – DEC 2021 at Media Lines – Al Ain, UAE
                    <ul class="list-disc list-inside mt-2">
                        <li>Increased client followers and engagement using precise, data-driven targeting.</li>
                        <li>Developed and executed content strategies for diverse clients.</li>
                    </ul>
                </p>
                <p>
                    <strong>Marketing specialist & Graphic Design</strong> <br>
                    NOV 2016 – MAR 2018 at A to Z – Damascus, Syria
                    <ul class="list-disc list-inside mt-2">
                        <li>Increased engagement by 45% and follower growth by 20% on Instagram.</li>
                        <li>Designed and implemented cohesive visual identities for 17 clients.</li>
                    </ul>
                </p>
            </div>
        </section>

        <!-- Portfolio Section - Refined Design -->
        <section id="portfolio" class="w-full mb-12">
            <h2 class="text-2xl font-bold highlight-text mb-8 text-center">
                Portfolio
            </h2>

            <!-- Visual Identity & Branding Section -->
            <div class="section-card p-8 rounded-3xl shadow-lg mb-8">
                <h3 class="text-xl font-bold text-gray-900 mb-6 border-b-2 pb-2 border-blue-200">
                    <span class="highlight-text">1.</span> Visual Identity & Branding
                </h3>
                <p class="text-gray-600 mb-4">
                    Projects focused on building a complete visual identity from concept to final execution.
                </p>
                <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-10">
                    <!-- Project 1: Croissun Pastry -->
                    <div class="project-card p-6 rounded-3xl shadow-xl animate-delay-1" data-project-id="croissun-pastry">
                        <h4 class="text-xl font-semibold text-gray-900 mb-2">Croissun Pastry</h4>
                        <img src="https://placehold.co/600x400/C4801F/FFFFFF?text=CROISSUN+PASTRY" alt="Croissun Pastry Logo" class="rounded-md mb-4 w-full">
                        <p class="text-gray-600 mb-4 text-sm">
                            Developed a full visual identity for a pastry brand, from logo design and color palettes to business cards and product packaging.
                        </p>
                        <p class="text-xs text-gray-500">
                            <strong class="text-gray-700">Skills:</strong> Graphic Design, Branding, Logo Design, Packaging Design
                        </p>
                    </div>
                </div>
            </div>

            <!-- Content & Social Media Design Section -->
            <div class="section-card p-8 rounded-3xl shadow-lg mb-8">
                <h3 class="text-xl font-bold text-gray-900 mb-6 border-b-2 pb-2 border-blue-200">
                    <span class="highlight-text">2.</span> Content & Social Media Design
                </h3>
                <p class="text-gray-600 mb-4">
                    Projects involving the design and management of social media accounts, focusing on audience growth and engagement.
                </p>
                <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-10">
                    <!-- Project 2: Map Real Estate -->
                    <div class="project-card p-6 rounded-3xl shadow-xl animate-delay-2" data-project-id="map-real-estate">
                        <h4 class="text-xl font-semibold text-gray-900 mb-2">Map Real Estate</h4>
                        <img src="https://placehold.co/600x400/0A311A/FFFFFF?text=Map+Real+Estate+Instagram" alt="Map Real Estate Instagram" class="rounded-md mb-4 w-full">
                        <p class="text-gray-600 mb-4 text-sm">
                            Designed and managed the Instagram account for a real estate company, establishing a cohesive visual theme and content strategy to boost engagement and reach.
                        </p>
                        <p class="text-xs text-gray-500">
                            <strong class="text-gray-700">Skills:</strong> Social Media Design, Content Creation, Digital Marketing
                        </p>
                    </div>
                </div>
            </div>
            
            <!-- Event Management & Marketing Section -->
            <div class="section-card p-8 rounded-3xl shadow-lg mb-8">
                <h3 class="text-xl font-bold text-gray-900 mb-6 border-b-2 pb-2 border-blue-200">
                    <span class="highlight-text">3.</span> Event Management & Marketing
                </h3>
                <p class="text-gray-600 mb-4">
                    Projects showcasing my skills in planning, promoting, and managing events to maximize attendance and brand impact.
                </p>
                <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-10">
                    <!-- New Project: Music Festival Event Marketing -->
                    <div class="project-card p-6 rounded-3xl shadow-xl animate-delay-3" data-project-id="event-marketing">
                        <h4 class="text-xl font-semibold text-gray-900 mb-2">Event Marketing</h4>
                        <img src="https://placehold.co/600x400/805ad5/ffffff?text=Event+Marketing" alt="Music Festival Event Marketing" class="rounded-md mb-4 w-full">
                        <p class="text-gray-600 mb-4 text-sm">
                            Managed and executed a comprehensive marketing strategy for a music festival, including social media campaigns, influencer outreach, and digital advertising.
                        </p>
                        <p class="text-xs text-gray-500">
                            <strong class="text-gray-700">Skills:</strong> Event Marketing, Social Media Strategy, PR
                        </p>
                    </div>
                </div>
            </div>

            <!-- Print & Catalog Design Section - New Section -->
            <div class="section-card p-8 rounded-3xl shadow-lg mb-8">
                <h3 class="text-xl font-bold text-gray-900 mb-6 border-b-2 pb-2 border-blue-200">
                    <span class="highlight-text">4.</span> Print & Catalog Design
                </h3>
                <p class="text-gray-600 mb-4">
                    Projects highlighting my expertise in creating engaging print materials, including professional brochures, flyers, and catalogs.
                </p>
                <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-10">
                    <!-- New Project: Catalog Design -->
                    <div class="project-card p-6 rounded-3xl shadow-xl animate-delay-4" data-project-id="catalog-design">
                        <h4 class="text-xl font-semibold text-gray-900 mb-2">Catalog Design</h4>
                        <img src="https://placehold.co/600x400/D9D9D9/363636?text=Catalog+Design" alt="Catalog Design" class="rounded-md mb-4 w-full">
                        <p class="text-gray-600 mb-4 text-sm">
                            Created a visually appealing and well-organized product catalog, focusing on a clean layout, strong typography, and high-quality imagery to enhance the user experience.
                        </p>
                        <p class="text-xs text-gray-500">
                            <strong class="text-gray-700">Skills:</strong> Print Design, Typography, Layout, InDesign
                        </p>
                    </div>
                </div>
            </div>
        </section>

        <!-- Tools and Skills Section -->
        <section id="tools" class="w-full section-card p-10 rounded-3xl shadow-lg mb-12">
            <h2 class="text-2xl font-bold highlight-text mb-8 text-center">
                Tools & Skills
            </h2>
            <div class="grid grid-cols-2 md:grid-cols-3 gap-8 text-center">
                <!-- Adobe Creative Suite -->
                <div id="adobe-creative-suite-tool" class="flex flex-col items-center group cursor-pointer">
                    <svg xmlns="http://www.w3.org/2000/svg" class="w-16 h-16 text-blue-400 mb-2 transition-transform duration-300 group-hover:scale-110" viewBox="0 0 24 24" fill="currentColor">
                        <path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-1 15h2v-6h-2v6zm0-8h2V7h-2v2z"/>
                    </svg>
                    <p class="text-sm font-semibold text-gray-700">Adobe Creative Suite</p>
                    <p class="text-xs text-gray-500 mt-1">Design & Content Creation</p>
                </div>
                <!-- Details - initially hidden -->
                <div id="adobe-creative-suite-details" class="col-span-full hidden mt-4">
                    <ul class="flex justify-center space-x-4 flex-wrap">
                        <li class="bg-gray-100 px-3 py-1 rounded-full text-xs text-gray-600 font-medium">Photoshop</li>
                        <li class="bg-gray-100 px-3 py-1 rounded-full text-xs text-gray-600 font-medium">Illustrator</li>
                        <li class="bg-gray-100 px-3 py-1 rounded-full text-xs text-gray-600 font-medium">InDesign</li>
                        <li class="bg-gray-100 px-3 py-1 rounded-full text-xs text-gray-600 font-medium">Adobe XD</li>
                    </ul>
                </div>
                <!-- Video Editing -->
                <div id="video-editing-tool" class="flex flex-col items-center group cursor-pointer">
                    <svg xmlns="http://www.w3.org/2000/svg" class="w-16 h-16 text-blue-400 mb-2 transition-transform duration-300 group-hover:scale-110" viewBox="0 0 24 24" fill="currentColor">
                        <path d="M17 10.5V7c0-.55-.45-1-1-1H4c-.55 0-1 .45-1 1v10c0 .55.45 1 1 1h12c.55 0 1-.45 1-1v-3.5l4 4v-11l-4 4z"/>
                    </svg>
                    <p class="text-sm font-semibold text-gray-700">Video Editing</p>
                    <p class="text-xs text-gray-500 mt-1">Visual Content Creation</p>
                </div>
                <!-- Details - initially hidden -->
                <div id="video-editing-details" class="col-span-full hidden mt-4">
                    <ul class="flex justify-center space-x-4 flex-wrap">
                        <li class="bg-gray-100 px-3 py-1 rounded-full text-xs text-gray-600 font-medium">Premier Pro</li>
                        <li class="bg-gray-100 px-3 py-1 rounded-full text-xs text-gray-600 font-medium">CapCut</li>
                        <li class="bg-gray-100 px-3 py-1 rounded-full text-xs text-gray-600 font-medium">VN</li>
                    </ul>
                </div>
                <!-- Digital Advertising -->
                <div id="digital-advertising-tool" class="flex flex-col items-center group cursor-pointer">
                    <svg xmlns="http://www.w3.org/2000/svg" class="w-16 h-16 text-blue-400 mb-2 transition-transform duration-300 group-hover:scale-110" viewBox="0 0 24 24" fill="currentColor">
                        <path d="M20 2H4c-1.1 0-2 .9-2 2v16c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V4c0-1.1-.9-2-2-2zm-8 12H9v-2h3V8h-2V6h2v2h2v4h-4v2z"/>
                    </svg>
                    <p class="text-sm font-semibold text-gray-700">Digital Advertising</p>
                    <p class="text-xs text-gray-500 mt-1">Google & Meta Ads</p>
                </div>
                <!-- Details - initially hidden -->
                <div id="digital-advertising-details" class="col-span-full hidden mt-4">
                    <ul class="flex justify-center space-x-4 flex-wrap">
                        <li class="bg-gray-100 px-3 py-1 rounded-full text-xs text-gray-600 font-medium">Meta Ads</li>
                        <li class="bg-gray-100 px-3 py-1 rounded-full text-xs text-gray-600 font-medium">Snapchat Ads</li>
                        <li class="bg-gray-100 px-3 py-1 rounded-full text-xs text-gray-600 font-medium">Google Ads</li>
                        <li class="bg-gray-100 px-3 py-1 rounded-full text-xs text-gray-600 font-medium">TikTok Ads</li>
                        <li class="bg-gray-100 px-3 py-1 rounded-full text-xs text-gray-600 font-medium">LinkedIn Ads</li>
                    </ul>
                </div>
                <!-- CRM & Automation -->
                <div id="crm-automation-tool" class="flex flex-col items-center group cursor-pointer">
                    <svg xmlns="http://www.w3.org/2000/svg" class="w-16 h-16 text-blue-400 mb-2 transition-transform duration-300 group-hover:scale-110" viewBox="0 0 24 24" fill="currentColor">
                        <path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-2.5 13.5v-7h5v7h-5zM12 8a2 2 0 11-4 0 2 2 0 014 0zm0 8a3 3 0 11-6 0 3 3 0 016 0zm-2-2h4v-2h-4v2z"/>
                    </svg>
                    <p class="text-sm font-semibold text-gray-700">CRM & Automation</p>
                    <p class="text-xs text-gray-500 mt-1">Marketing Cloud, Automation</p>
                </div>
                <!-- Details - initially hidden -->
                <div id="crm-automation-details" class="col-span-full hidden mt-4">
                    <ul class="flex justify-center space-x-4 flex-wrap">
                        <li class="bg-gray-100 px-3 py-1 rounded-full text-xs text-gray-600 font-medium">Marketing Cloud</li>
                        <li class="bg-gray-100 px-3 py-1 rounded-full text-xs text-gray-600 font-medium">Salesforce</li>
                    </ul>
                </div>
                <!-- Photography -->
                <div class="flex flex-col items-center group">
                    <svg xmlns="http://www.w3.org/2000/svg" class="w-16 h-16 text-blue-400 mb-2 transition-transform duration-300 group-hover:scale-110" viewBox="0 0 24 24" fill="currentColor">
                        <path d="M12 12c1.1 0 2-.9 2-2s-.9-2-2-2-2 .9-2 2 .9 2 2 2zm-4 8c-1.1 0-2 .9-2 2s.9 2 2 2 2-.9 2-2-.9-2-2-2zm8 0c-1.1 0-2 .9-2 2s.9 2 2 2 2-.9 2-2-.9-2-2-2zm-4-4c-1.1 0-2 .9-2 2s.9 2 2 2 2-.9 2-2-.9-2-2-2zm8-4c-1.1 0-2 .9-2 2s.9 2 2 2 2-.9 2-2-.9-2-2-2zm-4-4c-1.1 0-2 .9-2 2s.9 2 2 2 2-.9 2-2-.9-2-2-2z"/>
                    </svg>
                    <p class="text-sm font-semibold text-gray-700">Photography</p>
                    <p class="text-xs text-gray-500 mt-1">Creative & Visual Concepts</p>
                </div>
                 <!-- General Skills -->
                <div class="flex flex-col items-center group">
                    <svg xmlns="http://www.w3.org/2000/svg" class="w-16 h-16 text-blue-400 mb-2 transition-transform duration-300 group-hover:scale-110" viewBox="0 0 24 24" fill="currentColor">
                        <path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm1 15h-2v-6h2v6zm0-8h-2V7h2v2z"/>
                    </svg>
                    <p class="text-sm font-semibold text-gray-700">Marketing Strategy</p>
                    <p class="text-xs text-gray-500 mt-1">Campaign Planning</p>
                </div>
            </div>
        </section>

        <!-- Contact Section -->
        <section id="contact" class="w-full section-card p-10 rounded-3xl shadow-lg">
            <h2 class="text-2xl font-bold highlight-text mb-8 text-center">
                Contact
            </h2>
            <div class="flex flex-col md:flex-row md:justify-center md:space-x-12 space-y-6 md:space-y-0 items-center">
                <div class="flex flex-col items-center space-y-2">
                    <!-- Email Icon -->
                    <a href="mailto:mohamadalashoush@gmail.com" class="flex flex-col items-center space-y-2 group transform hover:scale-110 transition-transform duration-300">
                        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-12 h-12 text-blue-400 group-hover:text-blue-600 group-hover:shadow-lg transition-colors">
                          <path stroke-linecap="round" stroke-linejoin="round" d="M21.75 6.75v10.5a2.25 2.25 0 0 1-2.25 2.25h-15a2.25 2.25 0 0 1-2.25-2.25V6.75m19.5 0A2.25 2.25 0 0 0 19.5 4.5h-15a2.25 2.25 0 0 0-2.25 2.25m19.5 0v.243a2.25 2.25 0 0 1-1.07 1.916l-7.5 4.615a2.25 2.25 0 0 1-2.36 0L3.32 8.91a2.25 2.25 0 0 1-1.07-1.916V6.75" />
                        </svg>
                        <span class="text-gray-600 group-hover:text-gray-900 transition-colors">Email</span>
                    </a>
                </div>
                <div class="flex flex-col items-center space-y-2">
                    <!-- LinkedIn Icon - URL updated for consistency -->
                    <a href="https://www.linkedin.com/in/mohamadalashoush/" target="_blank" class="flex flex-col items-center space-y-2 group transform hover:scale-110 transition-transform duration-300">
                        <svg class="h-12 w-12 text-blue-400 group-hover:text-blue-600 group-hover:shadow-lg transition-colors" fill="currentColor" viewBox="0 0 24 24">
                            <path d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.761s.784-1.761 1.75-1.761 1.75.79 1.75 1.761c0 .971-.784 1.761-1.75 1.761zm13.5 12.268h-3v-5.604c0-3.368-4-3.264-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z"/>
                        </svg>
                        <span class="text-gray-600 group-hover:text-gray-900 transition-colors">LinkedIn</span>
                    </a>
                </div>
                <div class="flex flex-col items-center space-y-2">
                    <!-- Phone Icon -->
                    <a href="tel:+971501855759" class="flex flex-col items-center space-y-2 group transform hover:scale-110 transition-transform duration-300">
                         <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="w-12 h-12 text-blue-400 group-hover:text-blue-600 group-hover:shadow-lg transition-colors">
                            <path d="M6.62 10.79c1.46 3.25 4.71 6.5 7.96 7.96l2.12-2.12c.32-.32.74-.43 1.13-.24 1.12.37 2.33.57 3.55.57.55 0 1 .45 1 1v3.5c0 .55-.45 1-1 1C10.76 23 2 14.24 2 3c0-.55.45-1 1-1h3.5c.55 0 1 .45 1 1 0 1.22.2 2.43.57 3.55.19.39.08.81-.24 1.13l-2.12 2.12z"/>
                        </svg>
                        <span class="text-gray-600 group-hover:text-gray-900 transition-colors">Phone</span>
                    </a>
                </div>
            </div>
        </section>

    </div>

    <!-- Modal (initially hidden) -->
    <div id="projectModal" class="modal">
        <!-- Modal content -->
        <div class="modal-content">
            <span class="close-button">&times;</span>
            <div id="modal-body" class="p-4">
                <h3 id="modal-title" class="text-2xl font-bold text-gray-900 mb-4"></h3>
                <img id="modal-image" src="" alt="" class="rounded-lg shadow-md mb-4 w-full">
                <p id="modal-description" class="text-gray-700"></p>
            </div>
        </div>
    </div>

    <script>
        // Smooth scroll for internal navigation links
        document.querySelectorAll('nav a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                document.querySelector(this.getAttribute('href')).scrollIntoView({
                    behavior: 'smooth'
                });
            });
        });

        // Intersection Observer for fade-in animations
        const sections = document.querySelectorAll('.section-card');
        const options = {
            root: null, // relative to the viewport
            threshold: 0.1 // 10% of the element must be visible
        };
        const observer = new IntersectionObserver((entries, observer) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('is-visible');
                    observer.unobserve(entry.target);
                }
            });
        }, options);
        sections.forEach(section => {
            observer.observe(section);
        });

        // Modal functionality for project cards
        const modal = document.getElementById('projectModal');
        const closeButton = document.querySelector('.close-button');
        const projectCards = document.querySelectorAll('.project-card');

        // Hardcoded project data to display in the modal
        const projectsData = {
            'croissun-pastry': {
                title: 'Croissun Pastry - Visual Identity',
                image: 'https://placehold.co/800x600/C4801F/FFFFFF?text=Croissun+Pastry+Details',
                description: 'Developed a comprehensive visual identity for "Croissun Pastry," a modern pastry brand. The project involved crafting a unique logo that merged the croissant and sun shapes, selecting a warm color palette to reflect the brand\'s inviting nature, and designing various brand assets like business cards, product packaging, and social media templates. The goal was to create a cohesive and memorable brand presence that communicated quality and delight.'
            },
            'map-real-estate': {
                title: 'Map Real Estate - Social Media Strategy',
                image: 'https://placehold.co/800x600/0A311A/FFFFFF?text=Map+Real+Estate+Details',
                description: 'Managed and designed the Instagram account for "Map Real Estate," a real estate and construction company in Kuwait. The project focused on boosting engagement and follower growth through a data-driven content strategy. I created a consistent visual theme, designed engaging infographics, and optimized posting times to maximize reach. The efforts led to a significant increase in audience interaction and brand visibility in the local market.'
            },
            'catalog-design': {
                title: 'Catalog Design',
                image: 'https://placehold.co/800x600/D9D9D9/363636?text=Catalog+Design+Details',
                description: 'Created a visually appealing and well-organized product catalog for a fashion brand, focusing on a clean layout, strong typography, and high-quality imagery to enhance the user experience. This project highlights my skills in print design and production preparation.'
            },
            'event-marketing': {
                title: 'Event Marketing',
                image: 'https://placehold.co/800x600/805ad5/ffffff?text=Event+Marketing+Details',
                description: 'Planned and executed a comprehensive digital marketing campaign for a local music festival. The campaign included creating promotional social media content, managing paid ads on Meta and Google platforms, and coordinating with local influencers to boost ticket sales and brand awareness. The efforts resulted in a 30% increase in ticket sales and a significant rise in social media engagement.'
            }
        };

        projectCards.forEach(card => {
            card.addEventListener('click', () => {
                const projectId = card.getAttribute('data-project-id');
                const project = projectsData[projectId];
                if (project) {
                    document.getElementById('modal-title').textContent = project.title;
                    document.getElementById('modal-image').src = project.image;
                    document.getElementById('modal-image').alt = project.title;
                    document.getElementById('modal-description').textContent = project.description;
                    modal.style.display = 'flex';
                    modal.style.alignItems = 'center';
                    modal.style.justifyContent = 'center';
                }
            });
        });

        // Close the modal when the close button is clicked
        closeButton.addEventListener('click', () => {
            modal.style.display = 'none';
        });

        // Close the modal when clicking outside of it
        window.addEventListener('click', (event) => {
            if (event.target === modal) {
                modal.style.display = 'none';
            }
        });

        // Function to toggle visibility of details for a specific tool
        function toggleToolDetails(toolId) {
            const details = document.getElementById(toolId + '-details');
            details.classList.toggle('hidden');
        }

        // Add event listeners for tools
        document.getElementById('adobe-creative-suite-tool').addEventListener('click', () => toggleToolDetails('adobe-creative-suite'));
        document.getElementById('video-editing-tool').addEventListener('click', () => toggleToolDetails('video-editing'));
        document.getElementById('digital-advertising-tool').addEventListener('click', () => toggleToolDetails('digital-advertising'));
        document.getElementById('crm-automation-tool').addEventListener('click', () => toggleToolDetails('crm-automation'));
    </script>
</body>
</html>
