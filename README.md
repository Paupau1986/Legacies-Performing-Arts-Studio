<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Legacies Performing Arts Studios - Mentorship Program</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #f8f8f8; /* Light background */
            color: #333;
        }
        .section-title {
            position: relative;
            display: inline-block;
            padding-bottom: 8px;
            margin-bottom: 24px;
        }
        .section-title::after {
            content: '';
            position: absolute;
            left: 0;
            bottom: 0;
            width: 50%;
            height: 3px;
            background-color: #A0522D; /* Sienna-like color for accent */
            border-radius: 9999px;
        }
        .skill-card {
            transition: transform 0.3s ease-in-out, box-shadow 0.3s ease-in-out;
        }
        .skill-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
        }
        /* Custom modal styles */
        .modal {
            display: none; /* Hidden by default */
            position: fixed; /* Stay in place */
            z-index: 1000; /* Sit on top */
            left: 0;
            top: 0;
            width: 100%; /* Full width */
            height: 100%; /* Full height */
            overflow: auto; /* Enable scroll if needed */
            background-color: rgba(0,0,0,0.6); /* Black w/ opacity */
            justify-content: center;
            align-items: center;
        }
        .modal-content {
            background-color: #fff;
            margin: auto;
            padding: 30px;
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.3);
            max-width: 500px;
            width: 90%;
            text-align: center;
            position: relative;
        }
        .close-button {
            position: absolute;
            top: 10px;
            right: 15px;
            color: #aaa;
            font-size: 28px;
            font-weight: bold;
            cursor: pointer;
        }
        .close-button:hover,
        .close-button:focus {
            color: #333;
            text-decoration: none;
            cursor: pointer;
        }
        /* Loading spinner for LLM interaction */
        .loader {
            border: 4px solid #f3f3f3;
            border-top: 4px solid #3498db;
            border-radius: 50%;
            width: 30px;
            height: 30px;
            animation: spin 1s linear infinite;
            display: none; /* Hidden by default */
            margin: 0 auto;
        }
        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
    </style>
</head>
<body class="antialiased">

    <!-- Modal Structure -->
    <div id="promoModal" class="modal">
        <div class="modal-content">
            <span class="close-button" onclick="closeModal()">&times;</span>
            <h2 class="text-2xl font-bold text-gray-800 mb-4">🎉 Special Offer! 🎉</h2>
            <p class="text-lg text-gray-700 mb-6">Be one of the **first 10 participants** to enroll in our Mentorship Training Certification Program and get **FREE enrollment!**</p>
            <button onclick="closeModal()" class="bg-blue-600 hover:bg-blue-700 text-white font-semibold py-3 px-6 rounded-full shadow-lg transition duration-300 ease-in-out">Got It!</button>
        </div>
    </div>

    <!-- Header Section -->
    <header class="bg-white shadow-md py-4 px-6 md:px-12 flex justify-between items-center rounded-b-lg">
        <div class="flex items-center">
            <img src="https://placehold.co/60x60/A0522D/ffffff?text=LPA" alt="Legacies Performing Arts Studios Logo" class="h-12 w-12 mr-3 rounded-full">
            <div>
                <h1 class="text-2xl md:text-3xl font-extrabold text-gray-900">Legacies Performing Arts Studios</h1>
                <p class="text-sm md:text-base text-gray-600">Empowering Artists, Building Legacies</p>
            </div>
        </div>
        <nav>
            <ul class="flex space-x-4">
                <li><a href="#program" class="text-gray-700 hover:text-blue-600 font-medium transition duration-300">Program</a></li>
                <li><a href="#mentorship-areas" class="text-gray-700 hover:text-blue-600 font-medium transition duration-300">Areas</a></li>
                <li><a href="#ask-mentor" class="text-gray-700 hover:text-blue-600 font-medium transition duration-300">Ask a Mentor</a></li>
                <li><a href="#contact" class="text-gray-700 hover:text-blue-600 font-medium transition duration-300">Contact</a></li>
            </ul>
        </nav>
    </header>

    <!-- Hero Section -->
    <section class="relative bg-gradient-to-r from-blue-600 to-purple-700 text-white py-20 md:py-28 text-center rounded-b-xl shadow-xl mx-4 mt-8">
        <div class="container mx-auto px-6">
            <h2 class="text-4xl md:text-6xl font-extrabold leading-tight mb-6 animate-pulse">
                Unlock Your Artistic Potential!
            </h2>
            <p class="text-lg md:text-xl mb-10 max-w-3xl mx-auto">
                Join our **Mentorship Training Certification Program** and transform your passion into a certified skill.
            </p>
            <button onclick="openModal()" class="bg-yellow-400 hover:bg-yellow-500 text-gray-900 font-bold py-4 px-10 rounded-full shadow-lg text-lg uppercase tracking-wide transition duration-300 ease-in-out transform hover:scale-105">
                First 10 Participants FREE! Learn More!
            </button>
        </div>
    </section>

    <!-- Program Overview Section -->
    <section id="program" class="container mx-auto px-6 py-16 md:py-24">
        <h3 class="text-3xl md:text-4xl font-bold text-gray-800 mb-8 text-center section-title mx-auto">
            About Our Program
        </h3>
        <div class="grid md:grid-cols-2 gap-12 items-center">
            <div class="text-lg text-gray-700 leading-relaxed">
                <p class="mb-6">
                    Are you an **undergrad or senior high school student** with a burning passion for the arts? Or perhaps a **non-professional aged 18+** eager to kickstart your artistic journey? Our **Mentorship Training Certification Program** is your gateway to success!
                </p>
                <p class="mb-6">
                    Through comprehensive seminars and hands-on workshops, you'll gain invaluable guidance and practical experience from industry experts. This program is specifically designed for **skill development**, helping you to gain confidence, refine your craft, and prepare for a fulfilling career in the performing arts.
                </p>
                <p class="font-semibold text-blue-700">
                    Receive a **valuable professional certification** upon completion, recognizing your dedication and enhanced abilities.
                </p>
            </div>
            <div class="relative w-full h-64 md:h-96 rounded-xl overflow-hidden shadow-xl">
                <img src="https://placehold.co/800x600/DDA0DD/ffffff?text=Artistic+Growth" alt="Students learning and growing in an artistic environment" class="absolute inset-0 w-full h-full object-cover">
                <div class="absolute inset-0 bg-black bg-opacity-30 flex items-center justify-center">
                    <p class="text-white text-2xl font-bold text-center p-4">"Transforming Passion into Profession"</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Mentorship Areas Section -->
    <section id="mentorship-areas" class="bg-gray-100 py-16 md:py-24 rounded-xl mx-4 shadow-inner">
        <div class="container mx-auto px-6">
            <h3 class="text-3xl md:text-4xl font-bold text-gray-800 mb-12 text-center section-title mx-auto">
                Mentorship Areas
            </h3>
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">

                <!-- Modeling Card -->
                <div class="bg-white p-8 rounded-xl shadow-lg skill-card border border-gray-200">
                    <div class="flex items-center mb-4">
                        <img src="https://placehold.co/50x50/A0522D/ffffff?text=M" class="w-12 h-12 rounded-full mr-4" alt="Modeling Icon">
                        <h4 class="text-xl font-semibold text-gray-900">Modeling Mentorship</h4>
                    </div>
                    <p class="text-gray-700">Learn the ins and outs of the modeling world, from posing techniques to industry best practices and portfolio development.</p>
                </div>

                <!-- Musical Instrument Card -->
                <div class="bg-white p-8 rounded-xl shadow-lg skill-card border border-gray-200">
                    <div class="flex items-center mb-4">
                        <img src="https://placehold.co/50x50/A0522D/ffffff?text=MI" class="w-12 h-12 rounded-full mr-4" alt="Musical Instrument Icon">
                        <h4 class="text-xl font-semibold text-gray-900">Musical Instrument Mentorship</h4>
                    </div>
                    <p class="text-gray-700">Hone your instrumental prowess with expert guidance, mastering techniques and performance skills across various instruments.</p>
                </div>

                <!-- Talent Services Card -->
                <div class="bg-white p-8 rounded-xl shadow-lg skill-card border border-gray-200">
                    <div class="flex items-center mb-4">
                        <img src="https://placehold.co/50x50/A0522D/ffffff?text=TS" class="w-12 h-12 rounded-full mr-4" alt="Talent Services Icon">
                        <h4 class="text-xl font-semibold text-gray-900">Talent Services Mentorship</h4>
                    </div>
                    <p class="text-gray-700">Understand the business side of the arts, including self-promotion, networking, and navigating the industry to market your talent effectively.</p>
                </div>

                <!-- Singing Card -->
                <div class="bg-white p-8 rounded-xl shadow-lg skill-card border border-gray-200">
                    <div class="flex items-center mb-4">
                        <img src="https://placehold.co/50x50/A0522D/ffffff?text=S" class="w-12 h-12 rounded-full mr-4" alt="Singing Icon">
                        <h4 class="text-xl font-semibold text-gray-900">Singing Mentorship</h4>
                    </div>
                    <p class="text-gray-700">Refine your vocal techniques, expand your range, and develop powerful stage presence through personalized singing mentorship.</p>
                </div>

                <!-- Acting Card -->
                <div class="bg-white p-8 rounded-xl shadow-lg skill-card border border-gray-200">
                    <div class="flex items-center mb-4">
                        <img src="https://placehold.co/50x50/A0522D/ffffff?text=A" class="w-12 h-12 rounded-full mr-4" alt="Acting Icon">
                        <h4 class="text-xl font-semibold text-gray-900">Acting Mentorship</h4>
                    </div>
                    <p class="text-gray-700">Develop your acting craft for both stage and screen, exploring character development, improvisation, and performance techniques.</p>
                </div>

            </div>
        </div>
    </section>

    <!-- Ask a Mentor Section (New LLM Feature) -->
    <section id="ask-mentor" class="container mx-auto px-6 py-16 md:py-24 bg-white rounded-xl shadow-lg my-8">
        <h3 class="text-3xl md:text-4xl font-bold text-gray-800 mb-8 text-center section-title mx-auto">
            ✨ Ask a Mentor ✨
        </h3>
        <p class="text-lg text-gray-700 mb-8 text-center max-w-2xl mx-auto">
            Have a question about your artistic journey, career path, or need some inspiration? Our AI-powered mentor is here to offer insights and guidance.
        </p>
        <div class="flex flex-col items-center gap-6">
            <textarea id="mentorQuestion"
                      class="w-full md:w-3/4 p-4 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent transition duration-200 ease-in-out"
                      rows="5" placeholder="e.g., 'How can I overcome stage fright?', 'What's the best way to network in the music industry?', 'Give me some tips for building a strong portfolio.'"></textarea>
            <button id="askMentorBtn"
                    class="bg-purple-600 hover:bg-purple-700 text-white font-bold py-3 px-8 rounded-full shadow-md transition duration-300 ease-in-out transform hover:scale-105 flex items-center justify-center">
                Ask Mentor <span class="ml-2">✨</span>
            </button>
            <div id="mentorLoader" class="loader mt-4" style="display: none;"></div>
            <div id="mentorResponse" class="mt-8 p-6 bg-blue-50 border border-blue-200 rounded-xl shadow-inner text-gray-800 leading-relaxed max-w-3xl w-full" style="display: none;">
                <h4 class="font-semibold text-xl mb-3 text-blue-800">Mentor's Insight:</h4>
                <p id="mentorResponseText"></p>
            </div>
            <div id="mentorError" class="mt-4 p-4 bg-red-100 border border-red-400 text-red-700 rounded-lg max-w-3xl w-full" style="display: none;">
                <p>An error occurred. Please try again later.</p>
            </div>
        </div>
    </section>

    <!-- Call to Action / Contact Section -->
    <section id="contact" class="bg-blue-700 text-white py-16 md:py-24 text-center rounded-t-xl mx-4 mb-8 shadow-xl">
        <div class="container mx-auto px-6">
            <h3 class="text-3xl md:text-4xl font-bold mb-6">Ready to Start Your Artistic Journey?</h3>
            <p class="text-lg md:text-xl mb-8 max-w-2xl mx-auto">
                Don't miss this incredible opportunity to train with the best and earn a valuable certification.
            </p>
            <a href="mailto:info@legaciesperformingarts.com" class="bg-white hover:bg-gray-200 text-blue-700 font-bold py-4 px-10 rounded-full shadow-lg text-lg uppercase tracking-wide transition duration-300 ease-in-out transform hover:scale-105">
                Inquire Now!
            </a>
            <p class="mt-8 text-sm opacity-80">
                Or call us at: (123) 456-7890 | Visit us at: Your Studio Address, Cebu City, Philippines
            </p>
        </div>
    </section>

    <!-- Footer -->
    <footer class="bg-gray-900 text-white py-8 px-6 md:px-12 text-center rounded-t-lg">
        <p>&copy; 2025 Legacies Performing Arts Studios. All rights reserved.</p>
        <p class="text-sm mt-2">Empowering Artists, Building Legacies in Cebu City.</p>
    </footer>

    <script>
        // Function to open the modal
        function openModal() {
            document.getElementById('promoModal').style.display = 'flex';
        }

        // Function to close the modal
        function closeModal() {
            document.getElementById('promoModal').style.display = 'none';
        }

        // Close the modal if the user clicks anywhere outside of the modal content
        window.onclick = function(event) {
            const modal = document.getElementById('promoModal');
            if (event.target == modal) {
                modal.style.display = 'none';
            }
        }

        // LLM Integration for "Ask a Mentor"
        document.getElementById('askMentorBtn').addEventListener('click', async () => {
            const questionInput = document.getElementById('mentorQuestion');
            const mentorResponseDiv = document.getElementById('mentorResponse');
            const mentorResponseText = document.getElementById('mentorResponseText');
            const mentorLoader = document.getElementById('mentorLoader');
            const mentorError = document.getElementById('mentorError');

            const prompt = questionInput.value.trim();

            if (!prompt) {
                mentorResponseText.textContent = "Please enter a question to ask your mentor.";
                mentorResponseDiv.style.display = 'block';
                mentorError.style.display = 'none';
                return;
            }

            // Show loader, hide previous response/error
            mentorLoader.style.display = 'block';
            mentorResponseDiv.style.display = 'none';
            mentorError.style.display = 'none';
            mentorResponseText.textContent = ''; // Clear previous text

            try {
                let chatHistory = [];
                chatHistory.push({ role: "user", parts: [{ text: `As a supportive and knowledgeable mentor in the performing arts, provide a concise and encouraging answer to the following question: "${prompt}"` }] });
                const payload = { contents: chatHistory };
                const apiKey = ""; // Canvas will automatically provide the API key
                const apiUrl = `https://generativelanguage.googleapis.com/v1beta/models/gemini-2.0-flash:generateContent?key=${apiKey}`;

                const response = await fetch(apiUrl, {
                    method: 'POST',
                    headers: { 'Content-Type': 'application/json' },
                    body: JSON.stringify(payload)
                });

                if (!response.ok) {
                    throw new Error(`HTTP error! status: ${response.status}`);
                }

                const result = await response.json();

                if (result.candidates && result.candidates.length > 0 &&
                    result.candidates[0].content && result.candidates[0].content.parts &&
                    result.candidates[0].content.parts.length > 0) {
                    const text = result.candidates[0].content.parts[0].text;
                    mentorResponseText.textContent = text;
                    mentorResponseDiv.style.display = 'block';
                } else {
                    mentorError.style.display = 'block';
                    console.error("Unexpected API response structure:", result);
                }
            } catch (error) {
                mentorError.style.display = 'block';
                console.error("Error calling Gemini API:", error);
            } finally {
                mentorLoader.style.display = 'none'; // Hide loader
            }
        });
    </script>
</body>
</html>
