<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>American Sound GitHub Banner</title>
    <style>
        body {
            margin: 0;
            padding: 20px;
            background: #f6f8fa;
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
        }
        
        .banner {
            width: 100%;
            max-width: 1280px;
            height: 320px;
            margin: 0 auto;
            background: linear-gradient(135deg, #1e3a8a 0%, #3b82f6 100%);
            position: relative;
            overflow: hidden;
            border-radius: 12px;
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.1);
        }
        
        .banner::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: radial-gradient(circle at 30% 70%, rgba(255, 255, 255, 0.1) 0%, transparent 50%);
        }
        
        .banner::after {
            content: '';
            position: absolute;
            top: -50%;
            right: -20%;
            width: 600px;
            height: 600px;
            background: radial-gradient(circle, rgba(255, 255, 255, 0.05) 0%, transparent 70%);
            border-radius: 50%;
        }
        
        .content {
            position: relative;
            z-index: 2;
            display: flex;
            align-items: center;
            justify-content: space-between;
            height: 100%;
            padding: 0 60px;
        }
        
        .logo-section {
            display: flex;
            align-items: center;
            gap: 30px;
        }
        
        .logo {
            height: 120px;
            width: auto;
            filter: brightness(0) invert(1);
        }
        
        .text-content {
            display: none;
        }
        
        .company-name {
            font-size: 4.5rem;
            font-weight: 700;
            margin: 0;
            text-shadow: 0 2px 8px rgba(0, 0, 0, 0.3);
            letter-spacing: -0.02em;
        }
        
        .tagline {
            display: none;
        }
        
        .github-info {
            text-align: center;
            color: white;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
        }
        
        .repo-url {
            font-size: 1.4rem;
            opacity: 0.9;
            margin: 0;
            font-family: 'SF Mono', Monaco, monospace;
            background: rgba(255, 255, 255, 0.1);
            padding: 12px 20px;
            border-radius: 6px;
            backdrop-filter: blur(10px);
            white-space: nowrap;
        }
        
        .stats {
            display: none;
        }
        
        .stat {
            text-align: center;
        }
        
        .stat-number {
            font-size: 1.5rem;
            font-weight: 600;
            display: block;
            margin-bottom: 4px;
        }
        
        .stat-label {
            font-size: 0.9rem;
            opacity: 0.8;
            text-transform: uppercase;
            letter-spacing: 0.05em;
        }
        
        .wave-pattern {
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            height: 60px;
            background: linear-gradient(90deg, 
                rgba(255, 255, 255, 0.1) 0%, 
                rgba(255, 255, 255, 0.05) 25%, 
                rgba(255, 255, 255, 0.1) 50%, 
                rgba(255, 255, 255, 0.05) 75%, 
                rgba(255, 255, 255, 0.1) 100%);
            background-size: 200px 100%;
            animation: wave 3s ease-in-out infinite;
        }
        
        @keyframes wave {
            0%, 100% { background-position: 0% 0%; }
            50% { background-position: 100% 0%; }
        }
        
        .download-section {
            margin-top: 30px;
            text-align: center;
        }
        
        .download-btn {
            display: inline-block;
            background: #1e3a8a;
            color: white;
            padding: 12px 24px;
            text-decoration: none;
            border-radius: 8px;
            font-weight: 500;
            transition: background 0.3s ease;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
        }
        
        .download-btn:hover {
            background: #1e40af;
            transform: translateY(-1px);
        }
        
        .instructions {
            margin-top: 20px;
            padding: 20px;
            background: white;
            border-radius: 8px;
            border-left: 4px solid #3b82f6;
        }
        
        .instructions h3 {
            color: #1e3a8a;
            margin-top: 0;
        }
        
        .instructions code {
            background: #f1f5f9;
            padding: 2px 6px;
            border-radius: 4px;
            font-family: 'SF Mono', Monaco, monospace;
        }
    </style>
</head>
<body>
    <div class="banner">
        <div class="wave-pattern"></div>
        <div class="content">
            <div class="logo-section">
                <svg class="logo" viewBox="0 0 400 100" xmlns="http://www.w3.org/2000/svg">
                    <!-- Recreated American Sound logo in SVG -->
                    <g fill="currentColor">
                        <!-- Speed lines -->
                        <rect x="0" y="20" width="60" height="4"/>
                        <rect x="0" y="30" width="70" height="4"/>
                        <rect x="0" y="40" width="80" height="4"/>
                        <rect x="0" y="50" width="70" height="4"/>
                        <rect x="0" y="60" width="60" height="4"/>
                        
                        <!-- American text -->
                        <text x="90" y="45" font-family="Arial, sans-serif" font-size="24" font-weight="bold" font-style="italic">American</text>
                        
                        <!-- Sound text -->
                        <text x="90" y="70" font-family="Arial, sans-serif" font-size="18" font-weight="bold">SOUND</text>
                        

                    </g>
                </svg>
                
                <div class="text-content">
                    <h1 class="company-name">American Sound</h1>
                </div>
            </div>
            
            <div class="github-info">
                <p class="repo-url">github.com/american-sound</p>
            </div>
        </div>
    </div>
    
    <div class="download-section">
        <a href="#" class="download-btn" onclick="downloadBanner()">Download Banner (1280x320)</a>
    </div>
    
    <div class="instructions">
        <h3>How to use this banner:</h3>
        <ol>
            <li>Click the download button above to save the banner image</li>
            <li>Go to your GitHub repository: <code>github.com/american-sound</code></li>
            <li>Create or edit your <code>README.md</code> file</li>
            <li>Upload the banner image to your repository</li>
            <li>Add this markdown at the top of your README: <code>![American Sound Banner](./banner.png)</code></li>
        </ol>
        <p><strong>Pro tip:</strong> You can also host the image elsewhere and link directly to it, or use GitHub's repository social preview feature in Settings > General.</p>
    </div>

    <script>
        function downloadBanner() {
            // Create a canvas to render the banner
            const canvas = document.createElement('canvas');
            const ctx = canvas.getContext('2d');
            canvas.width = 1280;
            canvas.height = 320;
            
            // Create gradient background
            const gradient = ctx.createLinearGradient(0, 0, canvas.width, canvas.height);
            gradient.addColorStop(0, '#1e3a8a');
            gradient.addColorStop(1, '#3b82f6');
            
            ctx.fillStyle = gradient;
            ctx.fillRect(0, 0, canvas.width, canvas.height);
            
            // Add company name
            ctx.fillStyle = 'white';
            ctx.font = 'bold 72px Arial, sans-serif';
            ctx.textAlign = 'center';
            ctx.fillText('American Sound', canvas.width / 2, canvas.height / 2 - 20);
            
            // Add tagline
            ctx.font = '28px Arial, sans-serif';
            ctx.fillText('Professional Audio Solutions', canvas.width / 2, canvas.height / 2 + 30);
            
            // Add GitHub URL
            ctx.font = '24px monospace';
            ctx.fillText('github.com/american-sound', canvas.width / 2, canvas.height - 40);
            
            // Download the image
            const link = document.createElement('a');
            link.download = 'american-sound-github-banner.png';
            link.href = canvas.toDataURL();
            link.click();
        }
    </script>
</body>
</html>

# dev-guide
Main repository for assets, documentation, licensing info, discussion, and support for community open-source module development
