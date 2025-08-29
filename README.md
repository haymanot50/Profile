<!DOCTYPE html>
<html lang="en" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Haymanot Abera - IT Professional & Backend Developer</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;700&display=swap" rel="stylesheet">
    <!-- Chosen Palette: Warm Neutrals -->
    <!-- Application Structure Plan: A single-page portfolio layout with a sticky navigation bar for easy access to distinct sections (About, Skills, Vision, Connect). This structure is chosen over a linear document to provide a better user experience for potential employers, allowing them to quickly navigate to the information they need. Interactive filtering for skills makes the profile more engaging and easier to parse than a static table. -->
    <!-- Visualization & Content Choices: Report Info: Skills Table -> Goal: Organize/Inform -> Presentation: Interactive Card Grid -> Interaction: Category-based filtering -> Justification: More engaging and user-friendly than a static table, allows for quick assessment of skills in a specific area. -> Library/Method: Vanilla JS & Tailwind CSS. Report Info: Project Vision List -> Goal: Inform -> Presentation: Icon-based Cards -> Interaction: Hover effects -> Justification: Visually breaks up text and presents future goals in a more appealing format. -> Library/Method: Tailwind CSS. -->
    <!-- CONFIRMATION: NO SVG graphics used. NO Mermaid JS used. -->
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #E6E6FA;
            color: #1a1a1a;
        }
        .skill-card {
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        .skill-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05);
        }
        .nav-link {
            position: relative;
            transition: color 0.3s ease;
        }
        .nav-link::after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            bottom: -4px;
            left: 50%;
            transform: translateX(-50%);
            background-color: #4A90E2;
            transition: width 0.3s ease;
        }
        .nav-link:hover::after, .nav-link.active::after {
            width: 100%;
        }
        .filter-btn.active {
            background-color: #4A90E2;
            color: white;
        }
    </style>
</head>
<body class="antialiased">

    <header class="bg-white/80 backdrop-blur-lg sticky top-0 z-50 shadow-sm">
        <nav class="container mx-auto px-6 py-4 flex justify-between items-center">
            <div class="text-xl font-bold text-gray-800">Haymanot Abera</div>
            <div class="hidden md:flex space-x-8">
                <a href="#about" class="nav-link text-gray-600 hover:text-gray-900 font-medium">About</a>
                <a href="#skills" class="nav-link text-gray-600 hover:text-gray-900 font-medium">Skills</a>
                <a href="#vision" class="nav-link text-gray-600 hover:text-gray-900 font-medium">Vision</a>
                <a href="#connect" class="nav-link text-gray-600 hover:text-gray-900 font-medium">Connect</a>
            </div>
        </nav>
    </header>

    <main class="container mx-auto px-6 py-8 md:py-16">

        <section id="hero" class="text-center py-16">
            <img src="https://placehold.co/150x150/EFEFEF/333333?text=HA" alt="Haymanot Abera" class="w-36 h-36 mx-auto rounded-full shadow-lg mb-6 ring-4 ring-white/50">
            <h1 class="text-4xl md:text-6xl font-bold text-gray-800">Hi there, I'm Haymanot Abera 👋</h1>
            <p class="mt-4 text-xl md:text-2xl text-gray-600">IT Professional & Backend Developer</p>
        </section>

        <section id="about" class="py-16">
            <div class="text-center mb-12">
                <h2 class="text-3xl font-bold text-gray-800">🚀 About Me</h2>
                <div class="w-24 h-1 bg-[#4A90E2] mx-auto mt-2"></div>
            </div>
            <div class="max-w-3xl mx-auto bg-white p-8 rounded-lg shadow-md">
                <p class="text-lg text-gray-700 leading-relaxed">
                    I am a passionate learner currently working as an IT professional at Commercial Bank of Ethiopia. I've earned a BSc in Computer Engineering. My journey into coding is driven by a deep fascination with building robust and scalable systems from the ground up. I find immense satisfaction in understanding the architecture behind applications and making them work seamlessly.
                </p>
                <p class="mt-4 text-lg text-gray-700 leading-relaxed">
                    My primary aim is to specialize in backend development, with a vision to build powerful, efficient, and secure web services. I am also keenly interested in the world of DevOps, aspiring to streamline development pipelines and bridge the gap between development and operations.
                </p>
            </div>
        </section>

        <section id="skills" class="py-16">
            <div class="text-center mb-12">
                <h2 class="text-3xl font-bold text-gray-800">🛠️ Skills & Technologies</h2>
                <p class="mt-2 text-gray-600">Here's a look at the technologies I'm proficient with. Use the filters to explore.</p>
            </div>
            
            <div id="skill-filters" class="flex flex-wrap justify-center gap-2 mb-8">
                <button class="filter-btn active px-4 py-2 bg-white text-gray-700 rounded-full shadow-sm font-medium transition-colors duration-300" data-filter="all">All</button>
                <button class="filter-btn px-4 py-2 bg-white text-gray-700 rounded-full shadow-sm font-medium transition-colors duration-300" data-filter="language">Languages</button>
                <button class="filter-btn px-4 py-2 bg-white text-gray-700 rounded-full shadow-sm font-medium transition-colors duration-300" data-filter="backend">Backend</button>
                <button class="filter-btn px-4 py-2 bg-white text-gray-700 rounded-full shadow-sm font-medium transition-colors duration-300" data-filter="database">Databases</button>
                <button class="filter-btn px-4 py-2 bg-white text-gray-700 rounded-full shadow-sm font-medium transition-colors duration-300" data-filter="devops">DevOps & IT</button>
                <button class="filter-btn px-4 py-2 bg-white text-gray-700 rounded-full shadow-sm font-medium transition-colors duration-300" data-filter="technology">Technologies</button>
            </div>

            <div id="skill-grid" class="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-6">
                <div class="skill-card bg-white p-6 rounded-lg shadow-md text-center" data-category="language"><span class="font-bold text-lg">Python</span></div>
                <div class="skill-card bg-white p-6 rounded-lg shadow-md text-center" data-category="language"><span class="font-bold text-lg">JavaScript</span></div>
                <div class="skill-card bg-white p-6 rounded-lg shadow-md text-center" data-category="language"><span class="font-bold text-lg">C++</span></div>
                <div class="skill-card bg-white p-6 rounded-lg shadow-md text-center" data-category="language"><span class="font-bold text-lg">Amharic</span></div>
                <div class="skill-card bg-white p-6 rounded-lg shadow-md text-center" data-category="language"><span class="font-bold text-lg">English</span></div>
                <div class="skill-card bg-white p-6 rounded-lg shadow-md text-center" data-category="backend"><span class="font-bold text-lg">Node.js</span></div>
                <div class="skill-card bg-white p-6 rounded-lg shadow-md text-center" data-category="backend"><span class="font-bold text-lg">Express.js</span></div>
                <div class="skill-card bg-white p-6 rounded-lg shadow-md text-center" data-category="backend"><span class="font-bold text-lg">Django</span></div>
                <div class="skill-card bg-white p-6 rounded-lg shadow-md text-center" data-category="backend"><span class="font-bold text-lg">Backend Development</span></div>
                <div class="skill-card bg-white p-6 rounded-lg shadow-md text-center" data-category="database"><span class="font-bold text-lg">PostgreSQL</span></div>
                <div class="skill-card bg-white p-6 rounded-lg shadow-md text-center" data-category="database"><span class="font-bold text-lg">MySQL</span></div>
                <div class="skill-card bg-white p-6 rounded-lg shadow-md text-center" data-category="database"><span class="font-bold text-lg">MongoDB</span></div>
                <div class="skill-card bg-white p-6 rounded-lg shadow-md text-center" data-category="database"><span class="font-bold text-lg">Oracle SQL Basics</span></div>
                <div class="skill-card bg-white p-6 rounded-lg shadow-md text-center" data-category="devops"><span class="font-bold text-lg">Docker</span></div>
                <div class="skill-card bg-white p-6 rounded-lg shadow-md text-center" data-category="devops"><span class="font-bold text-lg">Kubernetes</span></div>
                <div class="skill-card bg-white p-6 rounded-lg shadow-md text-center" data-category="devops"><span class="font-bold text-lg">CI/CD</span></div>
                <div class="skill-card bg-white p-6 rounded-lg shadow-md text-center" data-category="devops"><span class="font-bold text-lg">Linux</span></div>
                <div class="skill-card bg-white p-6 rounded-lg shadow-md text-center" data-category="devops"><span class="font-bold text-lg">System Administration</span></div>
                <div class="skill-card bg-white p-6 rounded-lg shadow-md text-center" data-category="devops"><span class="font-bold text-lg">ITIL Framework</span></div>
                <div class="skill-card bg-white p-6 rounded-lg shadow-md text-center" data-category="technology"><span class="font-bold text-lg">Big Data (Hadoop)</span></div>
                <div class="skill-card bg-white p-6 rounded-lg shadow-md text-center" data-category="technology"><span class="font-bold text-lg">Augmented Reality</span></div>
                <div class="skill-card bg-white p-6 rounded-lg shadow-md text-center" data-category="technology"><span class="font-bold text-lg">IoT</span></div>
                <div class="skill-card bg-white p-6 rounded-lg shadow-md text-center" data-category="technology"><span class="font-bold text-lg">IT Security</span></div>
                <div class="skill-card bg-white p-6 rounded-lg shadow-md text-center" data-category="technology"><span class="font-bold text-lg">Networking</span></div>
                <div class="skill-card bg-white p-6 rounded-lg shadow-md text-center" data-category="technology"><span class="font-bold text-lg">Hardware & Software</span></div>
                <div class="skill-card bg-white p-6 rounded-lg shadow-md text-center" data-category="tool"><span class="font-bold text-lg">Git</span></div>
                <div class="skill-card bg-white p-6 rounded-lg shadow-md text-center" data-category="tool"><span class="font-bold text-lg">GitHub</span></div>
                <div class="skill-card bg-white p-6 rounded-lg shadow-md text-center" data-category="tool"><span class="font-bold text-lg">Postman</span></div>
            </div>
        </section>

        <section id="vision" class="py-16">
            <div class="text-center mb-12">
                <h2 class="text-3xl font-bold text-gray-800">🎯 My Vision & Projects</h2>
                <p class="mt-2 text-gray-600">I'm excited to work on projects that involve the following areas.</p>
            </div>
            <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-8">
                <div class="skill-card bg-white p-6 rounded-lg shadow-md text-center">
                    <div class="text-4xl mb-4">🔄</div>
                    <h3 class="text-xl font-bold mb-2">RESTful APIs</h3>
                    <p class="text-gray-600">Designing and implementing efficient and well-documented APIs.</p>
                </div>
                <div class="skill-card bg-white p-6 rounded-lg shadow-md text-center">
                    <div class="text-4xl mb-4">🧩</div>
                    <h3 class="text-xl font-bold mb-2">Microservices</h3>
                    <p class="text-gray-600">Developing scalable, independent services that communicate effectively.</p>
                </div>
                <div class="skill-card bg-white p-6 rounded-lg shadow-md text-center">
                    <div class="text-4xl mb-4">⚙️</div>
                    <h3 class="text-xl font-bold mb-2">CI/CD Pipelines</h3>
                    <p class="text-gray-600">Automating build, test, and deployment processes for efficiency.</p>
                </div>
                <div class="skill-card bg-white p-6 rounded-lg shadow-md text-center">
                    <div class="text-4xl mb-4">📦</div>
                    <h3 class="text-xl font-bold mb-2">Containerization</h3>
                    <p class="text-gray-600">Using Docker to package applications for seamless deployment.</p>
                </div>
            </div>
        </section>

    </main>
    
    <footer id="connect" class="bg-gray-800 text-white py-12">
        <div class="container mx-auto px-6 text-center">
            <h2 class="text-3xl font-bold">📫 Let's Connect!</h2>
            <p class="mt-4 max-w-2xl mx-auto">I'm always open to collaborating on new projects and sharing knowledge. Feel free to reach out!</p>
            <div class="flex justify-center space-x-6 mt-8">
                 <a href="https://www.linkedin.com/in/haymanot-abera-46526a22b" target="_blank" class="text-gray-400 hover:text-white transition-colors duration-300">
                    <span class="sr-only">LinkedIn</span>
                    <canvas id="linkedin-icon" width="32" height="32"></canvas>
                </a>
                <a href="https://github.com/haymanot50/" target="_blank" class="text-gray-400 hover:text-white transition-colors duration-300">
                    <span class="sr-only">GitHub</span>
                    <canvas id="github-icon" width="32" height="32"></canvas>
                </a>
                <a href="https://haymanotabera.wordpress.com" target="_blank" class="text-gray-400 hover:text-white transition-colors duration-300">
                    <span class="sr-only">Website</span>
                    <canvas id="website-icon" width="32" height="32"></canvas>
                </a>
                <a href="mailto:haymanotabera50@gmail.com" class="text-gray-400 hover:text-white transition-colors duration-300">
                    <span class="sr-only">Email</span>
                    <canvas id="email-icon" width="32" height="32"></canvas>
                </a>
            </div>
            <div class="mt-8 text-gray-500 text-sm">
                &copy; 2025 Haymanot Abera. All Rights Reserved.
            </div>
        </div>
    </footer>


    <script>
        document.addEventListener('DOMContentLoaded', () => {
            const skillFilters = document.getElementById('skill-filters');
            const skillCards = document.querySelectorAll('.skill-card[data-category]');
            
            skillFilters.addEventListener('click', (e) => {
                if (e.target.tagName === 'BUTTON') {
                    const filter = e.target.dataset.filter;

                    document.querySelector('.filter-btn.active').classList.remove('active');
                    e.target.classList.add('active');

                    skillCards.forEach(card => {
                        if (filter === 'all' || card.dataset.category === filter) {
                            card.style.display = 'block';
                        } else {
                            card.style.display = 'none';
                        }
                    });
                }
            });

            const navLinks = document.querySelectorAll('.nav-link');
            const sections = document.querySelectorAll('section[id]');

            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        navLinks.forEach(link => {
                            link.classList.toggle('active', link.getAttribute('href').substring(1) === entry.target.id);
                        });
                    }
                });
            }, { rootMargin: "-50% 0px -50% 0px" });

            sections.forEach(section => observer.observe(section));
            
            function drawIcon(canvasId, paths) {
                const canvas = document.getElementById(canvasId);
                const ctx = canvas.getContext('2d');
                ctx.fillStyle = '#9CA3AF';
                canvas.addEventListener('mouseenter', () => ctx.fillStyle = '#FFFFFF');
                canvas.addEventListener('mouseleave', () => ctx.fillStyle = '#9CA3AF');

                const scale = canvas.width / 32;
                ctx.scale(scale, scale);

                paths.forEach(pathData => {
                    const path = new Path2D(pathData);
                    ctx.fill(path);
                });
            }

            drawIcon('linkedin-icon', [
                'M27.5 0h-23C2 0 0 2 0 4.5v23C0 29.9 2 32 4.5 32h23c2.5 0 4.5-2.1 4.5-4.5v-23C32 2 30 0 27.5 0zM9.5 26h-4V12h4v14zM7.5 10.1c-1.4 0-2.6-1.2-2.6-2.6S6.1 5 7.5 5s2.6 1.2 2.6 2.6c0 1.5-1.2 2.5-2.6 2.5zm19 15.9h-4V19.5c0-1.6-.6-2.6-1.9-2.6-1.1 0-1.7.7-1.9 1.5-.1.3-.1.6-.1 1v6.6h-4V12h4v1.8c.5-1 1.5-2.1 3.6-2.1 2.6 0 4.5 1.7 4.5 5.3v9z'
            ]);

            drawIcon('github-icon', [
                'M16 0c-8.8 0-16 7.2-16 16 0 7.1 4.6 13.1 11 15.2.8.1 1.1-.3 1.1-.8 0-.4 0-.9-.1-1.4-4.5.9-5.4-2.2-5.4-2.2-.7-1.8-1.8-2.3-1.8-2.3-1.5-1 .1-1 .1-1 1.6.1 2.5 1.7 2.5 1.7 1.4 2.5 3.7 1.8 4.6 1.4.1-1.1.5-1.8.9-2.2-3.5-.4-7.2-1.7-7.2-7.8 0-1.7.6-3.2 1.7-4.3-.2-.4-.7-2.1.2-4.3 0 0 1.4-.4 4.5 1.6 1.3-.4 2.7-.6 4.2-.6 1.5 0 2.9.2 4.2.6 3.1-2 4.5-1.6 4.5-1.6.9 2.2.4 3.9.2 4.3 1.1 1.1 1.7 2.6 1.7 4.3 0 6.1-3.7 7.4-7.2 7.8.6.5 1.1 1.5 1.1 3.2 0 2.2 0 4.1-.1 4.7-.1.5.2.9 1.1.8C27.4 29.1 32 23.1 32 16c0-8.8-7.2-16-16-16z'
            ]);

            drawIcon('website-icon', [
                'M16 0c-8.8 0-16 7.2-16 16s7.2 16 16 16 16-7.2 16-16S24.8 0 16 0zm-10 16c0-2.2.9-4.3 2.5-5.8s3.6-2.5 5.8-2.5 4.3.9 5.8 2.5 2.5 3.6 2.5 5.8-.9 4.3-2.5 5.8-3.6 2.5-5.8 2.5-4.3-.9-5.8-2.5S6 18.2 6 16zM16 2.5c2.2 0 4.3.9 5.8 2.5S24.3 8.2 24.3 10.4H7.7c-.1-2.2.8-4.3 2.5-5.8S13.8 2.5 16 2.5zm0 27c-2.2 0-4.3-.9-5.8-2.5S7.7 23.8 7.7 21.6h16.6c.1 2.2-.8 4.3-2.5 5.8S18.2 29.5 16 29.5zM2.5 16c0-2.2.9-4.3 2.5-5.8h22c1.6 1.5 2.5 3.6 2.5 5.8s-.9 4.3-2.5 5.8h-22c-1.6-1.5-2.5-3.6-2.5-5.8z'
            ]);

            drawIcon('email-icon', [
                'M28 5H4C2.3 5 1 6.3 1 8v16c0 1.7 1.3 3 3 3h24c1.7 0 3-1.3 3-3V8c0-1.7-1.3-3-3-3zm-.4 2L16 14.8 4.4 7h23.2zM3 24V8.9l12.4 8.3c.4.2.8.4 1.2.4s.8-.1 1.2-.4L30 8.9V24H3z'
            ]);
        });
    </script>

</body>
</html>

