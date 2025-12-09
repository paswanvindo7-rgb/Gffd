<!DOCTYPE html>
<html>
<head>
    <title>YT Downloader</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            background: #f0f0f0;
            padding: 20px;
        }
        .container {
            max-width: 600px;
            margin: 0 auto;
            background: white;
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
        }
        input {
            width: 80%;
            padding: 12px;
            margin: 10px 0;
            border: 1px solid #ddd;
            border-radius: 5px;
        }
        button {
            background: #ff0000;
            color: white;
            border: none;
            padding: 12px 30px;
            border-radius: 5px;
            cursor: pointer;
            font-size: 16px;
        }
        .ad {
            background: #ffcc00;
            padding: 15px;
            margin: 20px 0;
            border-radius: 5px;
        }
        .info {
            background: #e6f7ff;
            padding: 15px;
            margin: 15px 0;
            border-radius: 5px;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>YouTube Video Downloader</h1>
        <p>Paste YouTube link and download video</p>
        
        <input type="text" id="url" placeholder="https://www.youtube.com/watch?v=...">
        <br>
        <button onclick="downloadVideo()">Download Now</button>
        
        <div class="info" id="info" style="display:none;">
            <h3>Video Information</h3>
            <p id="videoTitle">Video title will appear here</p>
            <div id="formats"></div>
        </div>
        
        <div class="ad">
            <h4>Advertisement</h4>
            <p>Try our premium downloader - Faster speeds!</p>
            <button style="background:#008CBA;">Learn More</button>
        </div>
        
        <div class="ad">
            <h4>Sponsored</h4>
            <p>Convert videos to MP3 instantly</p>
            <button style="background:#4CAF50;">Try Now</button>
        </div>
        
        <p style="color:red; font-size:12px; margin-top:20px;">
            Note: For educational purposes only. Respect copyrights.
        </p>
    </div>

    <script>
        function downloadVideo() {
            let url = document.getElementById('url').value;
            
            if(!url.includes('youtube.com') && !url.includes('youtu.be')) {
                alert('Please enter a valid YouTube URL');
                return;
            }
            
            // Show loading
            document.getElementById('info').style.display = 'block';
            document.getElementById('videoTitle').innerHTML = 'Processing...';
            
            // Simulate getting video info
            setTimeout(() => {
                // This is demo data - in real app, you would fetch from API
                document.getElementById('videoTitle').innerHTML = 'Sample Video Title';
                document.getElementById('formats').innerHTML = `
                    <button onclick="startDownload('360p')">MP4 360p</button>
                    <button onclick="startDownload('720p')">MP4 720p</button>
                    <button onclick="startDownload('1080p')">MP4 1080p</button>
                    <button onclick="startDownload('mp3')">MP3 Audio</button>
                `;
            }, 1500);
        }
        
        function startDownload(format) {
            alert('Downloading in ' + format + ' format...\n\nNote: This is a demo. In a real website, this would start the download.\n\nFor actual downloads, you need a backend server.');
            
            // In real website, redirect to download link
            // window.location.href = '/download?url=' + document.getElementById('url').value + '&format=' + format;
        }
        
        // Ad buttons
        document.querySelectorAll('.ad button').forEach(btn => {
            btn.onclick = () => {
                alert('Advertisement clicked! This would open advertiser website.');
            };
        });
    </script>
</body>
</html>
