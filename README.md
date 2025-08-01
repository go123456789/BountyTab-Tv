
<html class='ltr' dir='ltr' xmlns='http://www.w3.org/1999/xhtml' xmlns:b='http://www.google.com/2005/gml/b' xmlns:data='http://www.google.com/2005/gml/data' xmlns:expr='http://www.google.com/2005/gml/expr'>

<head>
    <script src='https://cdn.jsdelivr.net/npm/hls.js@test'></script>
    <style type='text/css'>
        @font-face {
            font-family: 'Josefin Sans';
            font-style: normal;
            font-weight: 400;
            font-display: swap;
            src: url(//fonts.gstatic.com/s/josefinsans/v33/Qw3PZQNVED7rKGKxtqIqX5E-AVSJrOCfjY46_DjQbMlhLzTs.woff2)format('woff2');
            unicode-range: U+0102-0103, U+0110-0111, U+0128-0129, U+0168-0169, U+01A0-01A1, U+01AF-01B0, U+0300-0301, U+0303-0304, U+0308-0309, U+0323, U+0329, U+1EA0-1EF9, U+20AB;
        }

        @font-face {
            font-family: 'Josefin Sans';
            font-style: normal;
            font-weight: 400;
            font-display: swap;
            src: url(//fonts.gstatic.com/s/josefinsans/v33/Qw3PZQNVED7rKGKxtqIqX5E-AVSJrOCfjY46_DjQbMhhLzTs.woff2)format('woff2');
            unicode-range: U+0100-02BA, U+02BD-02C5, U+02C7-02CC, U+02CE-02D7, U+02DD-02FF, U+0304, U+0308, U+0329, U+1D00-1DBF, U+1E00-1E9F, U+1EF2-1EFF, U+2020, U+20A0-20AB, U+20AD-20C0, U+2113, U+2C60-2C7F, U+A720-A7FF;
        }

        @font-face {
            font-family: 'Josefin Sans';
            font-style: normal;
            font-weight: 400;
            font-display: swap;
            src: url(//fonts.gstatic.com/s/josefinsans/v33/Qw3PZQNVED7rKGKxtqIqX5E-AVSJrOCfjY46_DjQbMZhLw.woff2)format('woff2');
            unicode-range: U+0000-00FF, U+0131, U+0152-0153, U+02BB-02BC, U+02C6, U+02DA, U+02DC, U+0304, U+0308, U+0329, U+2000-206F, U+20AC, U+2122, U+2191, U+2193, U+2212, U+2215, U+FEFF, U+FFFD;
        }
    </style>
    <style>
        :root {
            --bg-color: #000;
            --text-color: #fff;
            --category-bg: #222;
            --category-active: #9001b3;
        }

        body {
            margin: 0;
            background: var(--bg-color);
            color: var(--text-color);
            font-family: sans-serif;
            overflow-x: hidden;
        }

        .video-container {
            position: relative;
            width: 100%;
            height: 75vh;
            max-height: 500px;
            background: #000;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        video {
            width: 100%;
            height: 100%;
            object-fit: contain;
            display: block;
        }

        #posterImage {
            position: absolute;
            width: 100%;
            height: 100%;
            object-fit: contain;
            z-index: 1;
        }

        .live-badge {
            position: absolute;
            top: 10px;
            left: 10px;
            background-color: lab(36.46% 72.19 -78.54 / 0.568)10.62)0.62)0.62)0.62)967% 0.1045 164.944)9999999% -0.19315 0.08244)
            color: white;
            font-size: 14px;
            font-weight: bold;
            padding: 2px 6px;
            border-radius: 3px;
            line-height: 1.2;
            z-index: 10;
            animation: pulse 1s infinite;
        }

        @keyframes pulse {
            0% {
                opacity: 1;
                transform: scale(1);
            }
            50% {
                opacity: 0.8;
                transform: scale(1.05);
            }
            100% {
                opacity: 1;
                transform: scale(1);
            }
        }

        .controls {
            position: absolute;
            bottom: 10px;
            left: 50%;
            transform: translateX(-50%);
            display: flex;
            gap: 10px;
            background: rgba(0, 0, 0, 0.5);
            padding: 6px 12px;
            border-radius: 30px;
            z-index: 2;
        }

        .control-btn,
        .mute-btn {
            background: rgba(255, 255, 255, 0.2);
            color: white;
            border: none;
            width: 36px;
            height: 36px;
            border-radius: 50%;
            cursor: pointer;
        }

        .quality-select {
            border-radius: 20px;
            padding: 4px 10px;
            background: #1479ff;
            color: white;
            border: none;
            font-size: 12px;
        }

        .category-bar {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            padding: 10px;
            background: var(--category-bg);
            align-items: center;
        }

        .category-bar button {
            background: var(--category-bg);
            color: white;
            border: none;
            padding: 8px 14px;
            border-radius: 20px;
            cursor: pointer;
        }

        .category-bar button.active {
            background: var(--category-active);
        }

        .dark-toggle {
            margin-left: auto;
            padding: 8px 14px;
            border-radius: 20px;
            background: #444;
            color: white;
            border: none;
            cursor: pointer;
        }

        .channel-grid {
            display: grid;
            grid-template-columns: repeat(5, 1fr);
            gap: 5px;
            padding: 5px;
        }

        .channel {
            background: #111;
            text-align: center;
            padding: 10px;
            border-radius: 10px;
            cursor: pointer;
        }

        .channel img {
            width: 50px;
            height: 50px;
            object-fit: contain;
            border-radius: 5px;
        }

        .channel p {
            margin: 5px 0 0;
            color: #9001b3;
            font-size: 14px;
        }
    </style>
    <script src='https://cdnjs.cloudflare.com/ajax/libs/shaka-player/4.3.6/shaka-player.compiled.js'></script>
    <script src='https://cdn.jsdelivr.net/npm/hls.js@latest'></script>
    <style>
        :root {
            --bg-color: #000;
            --text-color: #fff;
            --category-bg: #222;
            --category-active: #4CAF50;
        }

        body {
            margin: 0;
            background: var(--bg-color);
            color: var(--text-color);
            font-family: sans-serif;
            overflow-x: hidden;
        }

        .video-container {
            position: relative;
            width: 100%;
            height: 75vh;
            max-height: 500px;
            background: #000;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        video {
            width: 100%;
            height: 100%;
            object-fit: contain;
            display: block;
        }

        #posterImage {
            position: absolute;
            width: 100%;
            height: 100%;
            object-fit: contain;
            z-index: 1;
        }

        .live-badge {
            position: absolute;
            top: 10px;
            left: 10px;
            background-color: #9001b3;
            color: white;
            font-size: 14px;
            font-weight: bold;
            padding: 2px 6px;
            border-radius: 3px;
            line-height: 1.2;
            z-index: 10;
            animation: pulse 1s infinite;
        }

        @keyframes pulse {
            0% {
                opacity: 1;
                transform: scale(1);
            }
            50% {
                opacity: 0.8;
                transform: scale(1.05);
            }
            100% {
                opacity: 1;
                transform: scale(1);
            }
        }

        .controls {
            position: absolute;
            bottom: 10px;
            left: 50%;
            transform: translateX(-50%);
            display: flex;
            gap: 10px;
            background: rgba(0, 0, 0, 0.5);
            padding: 6px 12px;
            border-radius: 30px;
            z-index: 2;
        }

        .control-btn,
        .mute-btn {
            background: rgba(255, 255, 255, 0.2);
            color: white;
            border: none;
            width: 36px;
            height: 36px;
            border-radius: 50%;
            cursor: pointer;
        }

        .quality-select {
            border-radius: 20px;
            padding: 4px 10px;
            background: #1479ff;
            color: white;
            border: none;
            font-size: 12px;
        }

        .category-bar {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            padding: 10px;
            background: var(--category-bg);
            align-items: center;
        }

        .category-bar button {
            background: var(--category-bg);
            color: white;
            border: none;
            padding: 8px 14px;
            border-radius: 20px;
            cursor: pointer;
        }

        .category-bar button.active {
            background: var(--category-active);
        }

        .dark-toggle {
            margin-left: auto;
            padding: 8px 14px;
            border-radius: 20px;
            background: #444;
            color: white;
            border: none;
            cursor: pointer;
        }

        .channel-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 5px;
            padding: 5px;
        }

        .channel {
            background: #111;
            text-align: center;
            padding: 10px;
            border-radius: 10px;
            cursor: pointer;
        }

        .channel img {
            width: 60px;
            height: 60px;
            object-fit: contain;
            border-radius: 10px;
        }

        .channel p {
            margin: 5px 0 0;
            color: red;
            font-size: 14px;
        }
    </style>
    <script src='https://cdn.jsdelivr.net/npm/hls.js@latest'></script>
    <style>
        <script src='https://cdn.jsdelivr.net/npm/nosleep.js@0.12.0/dist/NoSleep.min.js'></script> :root {
            --bg-color: #000;
            --text-color: #fff;
            --category-bg: #222;
            --category-active: #4CAF50;
        }

        body {
            margin: 0;
            background: var(--bg-color);
            color: var(--text-color);
            font-family: sans-serif;
            overflow-x: hidden;
        }

        .video-container {
            position: relative;
            width: 100%;
            height: 75vh;
            max-height: 500px;
            background: #000;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        video {
            width: 100%;
            height: 100%;
            object-fit: contain;
            display: block;
        }

        #posterImage {
            position: absolute;
            width: 100%;
            height: 100%;
            object-fit: contain;
            z-index: 1;
        }

        #loadingOverlay {
            position: absolute;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.7);
            color: red;
            font-size: 22px;
            display: none;
            align-items: center;
            justify-content: center;
            z-index: 9;
        }

        .live-badge {
            position: absolute;
            top: 10px;
            left: 10px;
            background-color: #9001b3;
            color: white;
            font-size: 14px;
            font-weight: bold;
            padding: 2px 6px;
            border-radius: 3px;
            line-height: 1.2;
            z-index: 10;
            animation: pulse 1s infinite;
        }

        @keyframes pulse {
            0% {
                opacity: 1;
                transform: scale(1);
            }
            50% {
                opacity: 0.8;
                transform: scale(1.05);
            }
            100% {
                opacity: 1;
                transform: scale(1);
            }
        }

        .controls {
            position: absolute;
            bottom: 10px;
            left: 50%;
            transform: translateX(-50%);
            display: flex;
            gap: 10px;
            background: rgba(0, 0, 0, 0.5);
            padding: 6px 12px;
            border-radius: 30px;
            z-index: 2;
        }

        .control-btn,
        .mute-btn {
            background: rgba(255, 255, 255, 0.2);
            color: white;
            border: none;
            width: 36px;
            height: 36px;
            border-radius: 50%;
            cursor: pointer;
        }

        .quality-select {
            border-radius: 20px;
            padding: 4px 10px;
            background: #1479ff;
            color: white;
            border: none;
            font-size: 12px;
        }

        .category-bar {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            padding: 10px;
            background: var(--category-bg);
            align-items: center;
        }

        .category-bar button {
            background: var(--category-bg);
            color: white;
            border: none;
            padding: 8px 14px;
            border-radius: 20px;
            cursor: pointer;
        }

        .category-bar button.active {
            background: var(--category-active);
        }

        .dark-toggle {
            margin-left: auto;
            padding: 8px 14px;
            border-radius: 20px;
            background: #444;
            color: white;
            border: none;
            cursor: pointer;
        }

        .channel-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 5px;
            padding: 5px;
        }

        .channel {
            background: #111;
            text-align: center;
            padding: 10px;
            border-radius: 10px;
            cursor: pointer;
        }

        .channel img {
            width: 80px;
            height: 80px;
            object-fit: contain;
            border-radius: 14px;
        }

        .channel p {
            margin: 5px 0 0;
            color: red;
            font-size: 14px;
        }
    </style>
    <script type='text/javascript'>
        //<![CDATA[

        var uri = window.location.toString();

        if (uri.indexOf("%3D", "%3D") > 0) {

            var clean_uri = uri.substring(0, uri.indexOf("%3D"));

            window.history.replaceState({}, document.title, clean_uri);

        }

        var uri = window.location.toString();

        if (uri.indexOf("%3D%3D", "%3D%3D") > 0) {

            var clean_uri = uri.substring(0, uri.indexOf("%3D%3D"));

            window.history.replaceState({}, document.title, clean_uri);

        }

        var uri = window.location.toString();

        if (uri.indexOf("&m=1", "&m=1") > 0) {

            var clean_uri = uri.substring(0, uri.indexOf("&m=1"));

            window.history.replaceState({}, document.title, clean_uri);

        }

        var uri = window.location.toString();

        if (uri.indexOf("?m=1", "?m=1") > 0) {

            var clean_uri = uri.substring(0, uri.indexOf("?m=1"));

            window.history.replaceState({}, document.title, clean_uri);

        }

        //]]>
    </script>
    <!-- Jquery Library and Font Awesome CDN -->
    <script src='https://ajax.googleapis.com/ajax/libs/jquery/2.2.4/jquery.min.js'></script>
    <link crossorigin='anonymous' href='https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.11.2/css/all.css' integrity='sha256-46qynGAkLSFpVbEBog43gvNhfrOj+BmwXdxFgVK/Kvc=' rel='stylesheet' />
    <meta content='width=device-width, initial-scale=1, minimum-scale=1, maximum-scale=1' name='viewport' />
    <meta content='text/html; charset=UTF-8' http-equiv='Content-Type' />
    <!-- Chrome, Firefox OS and Opera -->
    <meta content='#6c6cfe' name='theme-color' />
    <!-- Windows Phone -->
    <meta content='#6c6cfe' name='msapplication-navbutton-color' />
    <meta content='blogger' name='generator' />
    <link href='https://i.postimg.cc/ZY2S3qgL/photo-6071237273250285382-y.jpg' rel='icon' type='image/x-icon' />
    <link href='http://www.nadimrazatv.online/' rel='canonical' />
    <link rel="alternate" type="application/atom+xml" title="NadimRazaTV Official-free  live tv Stream platform Bangladesh 🇧🇩 - Atom" href="https://www.nadimrazatv.online/feeds/posts/default" />
    <link rel="alternate" type="application/rss+xml" title="NadimRazaTV Official-free  live tv Stream platform Bangladesh 🇧🇩 - RSS" href="https://www.nadimrazatv.online/feeds/posts/default?alt=rss" />
    <link rel="service.post" type="application/atom+xml" title="NadimRazaTV Official-free  live tv Stream platform Bangladesh 🇧🇩 - Atom" href="https://www.blogger.com/feeds/2001592501175586361/posts/default" />
    <link rel="me" href="https://www.blogger.com/profile/18012932550810378007" />
    <!--Can't find substitution for tag [blog.ieCssRetrofitLinks]-->
    <meta content='Welcome NadimRaza TV Free Platform 2024_2025_2026' name='description' />
    <meta content='http://www.nadimrazatv.online/' property='og:url' />
    <meta content='NadimRazaTV Official-free  live tv Stream platform Bangladesh 🇧🇩' property='og:title' />
    <meta content='Welcome NadimRaza TV Free Platform 2024_2025_2026' property='og:description' />
    <title>NadimRazaTV Official-tv Stream platform Bangladesh 🇧🇩
    </title>
    <meta content='hollywood dual audio movies, 300mb hd, Hindi Dubbed, English Movies, Full Movie, Full Movie Dual Audio, Full ovie Hollywood, PUNJABI MOVIES HD, RDXHD.ME, RDX HD, FULL PUNJABI MOVIES, BOLLYWOOD MOVIES, NEW PUNJABI MOVIES, FULL HD PUNJABI MOVIES,'
        name='keywords' />
    <link href='https://fonts.googleapis.com' rel='preconnect' />
    <link crossorigin='' href='https://fonts.gstatic.com' rel='preconnect' />
    <link href='https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;600;700&display=swap' rel='stylesheet' />
    <link href='//fonts.gstatic.com' rel='dns-prefetch' />
    <link href='//1.bp.blogspot.com' rel='dns-prefetch' />
    <link href='//2.bp.blogspot.com' rel='dns-prefetch' />
    <link href='//3.bp.blogspot.com' rel='dns-prefetch' />
    <link href='//4.bp.blogspot.com' rel='dns-prefetch' />
    <link href='//www.blogger.com' rel='dns-prefetch' />
    <link href='//dnjs.cloudflare.com' rel='dns-prefetch' />
    <link href='//pagead2.googlesyndication.com' rel='dns-prefetch' />
    <link href='//www.googletagmanager.com' rel='dns-prefetch' />
    <link href='//www.google-analytics.com' rel='dns-prefetch' />
    <link href='//connect.facebook.net' rel='dns-prefetch' />
    <link href='//c.disquscdn.com' rel='dns-prefetch' />
    <link href='//disqus.com' rel='dns-prefetch' />
    <meta content='text/html; charset=UTF-8' http-equiv='Content-Type' />
    <meta content='blogger' name='generator' />
    <link href='https://i.postimg.cc/ZY2S3qgL/photo-6071237273250285382-y.jpg' rel='icon' type='image/x-icon' />
    <link href='http://www.nadimrazatv.online/' rel='canonical' />
    <link rel="alternate" type="application/atom+xml" title="NadimRazaTV Official-free  live tv Stream platform Bangladesh 🇧🇩 - Atom" href="https://www.nadimrazatv.online/feeds/posts/default" />
    <link rel="alternate" type="application/rss+xml" title="NadimRazaTV Official-free  live tv Stream platform Bangladesh 🇧🇩 - RSS" href="https://www.nadimrazatv.online/feeds/posts/default?alt=rss" />
    <link rel="service.post" type="application/atom+xml" title="NadimRazaTV Official-free  live tv Stream platform Bangladesh 🇧🇩 - Atom" href="https://www.blogger.com/feeds/2001592501175586361/posts/default" />
    <link rel="me" href="https://www.blogger.com/profile/18012932550810378007" />
    <meta content='Welcome NadimRaza TV Free Platform 2024_2025_2026' name='description' />
    <!-- Metadata for Open Graph protocol. See http://ogp.me/. -->
    <meta content='website' property='og:type' />
    <meta content='NadimRazaTV Official-free  live tv Stream platform Bangladesh 🇧🇩' property='og:title' />
    <meta content='http://www.nadimrazatv.online/' property='og:url' />
    <meta content='Welcome NadimRaza TV Free Platform 2024_2025_2026' property='og:description' />
    <meta content='NadimRazaTV Official-free  live tv Stream platform Bangladesh 🇧🇩' property='og:site_name' />
    <meta content='summary_large_image' name='twitter:card' />
    <meta content='NadimRazaTV Official-free  live tv Stream platform Bangladesh 🇧🇩' name='twitter:title' />
    <meta content='http://www.nadimrazatv.online/' name='twitter:domain' />
    <meta content='Welcome NadimRaza TV Free Platform 2024_2025_2026' name='twitter:description' />
    <script type='application/ld+json'>
        {
            "@context": "http://schema.org",
            "@type": "WebSite",
            "name": "NadimRazaTV Official-free  live tv Stream platform Bangladesh 🇧🇩",
            "url": "http://www.nadimrazatv.online/",
            "potentialAction": {
                "@type": "SearchAction",
                "target": "http://www.nadimrazatv.online/search?q={search_term_string}",
                "query-input": "required name=search_term_string"
            }
        }
    </script>
    <!-- Font Awesome Free 5.11.2 -->
    <link href='https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.11.2/css/all.min.css' rel='stylesheet' />
    <!-- Theme Style CSS -->
    <style id='page-skin-1' type='text/css'>
        < !--
        /*
-----------------------------------------------
Blogger Template Style
Name:        Vegamovies
Version:     1.0.0 - Premium
Distributer:      Pro Templates
Author Url:  https://protemplates.in
-----------------------------------------------*/

        /*-- Google Fonts --*/

        @font-face {
            font-family: 'Raleway';
            font-style: italic;
            font-weight: 400;
            font-display: swap;
            src: local('Raleway Italic'), local(Raleway-Italic), url(https://fonts.gstatic.com/s/raleway/v14/1Ptsg8zYS_SKggPNyCg4Q4FqPfE.woff2) format("woff2");
            unicode-range: U+0100-024F, U+0259, U+1E00-1EFF, U+2020, U+20A0-20AB, U+20AD-20CF, U+2113, U+2C60-2C7F, U+A720-A7FF
        }

        @font-face {
            font-family: 'Raleway';
            font-style: italic;
            font-weight: 400;
            font-display: swap;
            src: local('Raleway Italic'), local(Raleway-Italic), url(https://fonts.gstatic.com/s/raleway/v14/1Ptsg8zYS_SKggPNyCg4TYFq.woff2) format("woff2");
            unicode-range: U+0000-00FF, U+0131, U+0152-0153, U+02BB-02BC, U+02C6, U+02DA, U+02DC, U+2000-206F, U+2074, U+20AC, U+2122, U+2191, U+2193, U+2212, U+2215, U+FEFF, U+FFFD
        }

        @font-face {
            font-family: 'Raleway';
            font-style: italic;
            font-weight: 500;
            font-display: swap;
            src: local('Raleway Medium Italic'), local(Raleway-MediumItalic), url(https://fonts.gstatic.com/s/raleway/v14/1Ptpg8zYS_SKggPNyCgwvqJ_DNCb_Vo.woff2) format("woff2");
            unicode-range: U+0100-024F, U+0259, U+1E00-1EFF, U+2020, U+20A0-20AB, U+20AD-20CF, U+2113, U+2C60-2C7F, U+A720-A7FF
        }

        @font-face {
            font-family: 'Raleway';
            font-style: italic;
            font-weight: 500;
            font-display: swap;
            src: local('Raleway Medium Italic'), local(Raleway-MediumItalic), url(https://fonts.gstatic.com/s/raleway/v14/1Ptpg8zYS_SKggPNyCgwvqJ_AtCb.woff2) format("woff2");
            unicode-range: U+0000-00FF, U+0131, U+0152-0153, U+02BB-02BC, U+02C6, U+02DA, U+02DC, U+2000-206F, U+2074, U+20AC, U+2122, U+2191, U+2193, U+2212, U+2215, U+FEFF, U+FFFD
        }

        @font-face {
            font-family: 'Raleway';
            font-style: italic;
            font-weight: 600;
            font-display: swap;
            src: local('Raleway SemiBold Italic'), local(Raleway-SemiBoldItalic), url(https://fonts.gstatic.com/s/raleway/v14/1Ptpg8zYS_SKggPNyCgwkqV_DNCb_Vo.woff2) format("woff2");
            unicode-range: U+0100-024F, U+0259, U+1E00-1EFF, U+2020, U+20A0-20AB, U+20AD-20CF, U+2113, U+2C60-2C7F, U+A720-A7FF
        }

        @font-face {
            font-family: 'Raleway';
            font-style: italic;
            font-weight: 600;
            font-display: swap;
            src: local('Raleway SemiBold Italic'), local(Raleway-SemiBoldItalic), url(https://fonts.gstatic.com/s/raleway/v14/1Ptpg8zYS_SKggPNyCgwkqV_AtCb.woff2) format("woff2");
            unicode-range: U+0000-00FF, U+0131, U+0152-0153, U+02BB-02BC, U+02C6, U+02DA, U+02DC, U+2000-206F, U+2074, U+20AC, U+2122, U+2191, U+2193, U+2212, U+2215, U+FEFF, U+FFFD
        }

        @font-face {
            font-family: 'Raleway';
            font-style: italic;
            font-weight: 700;
            font-display: swap;
            src: local('Raleway Bold Italic'), local(Raleway-BoldItalic), url(https://fonts.gstatic.com/s/raleway/v14/1Ptpg8zYS_SKggPNyCgw9qR_DNCb_Vo.woff2) format("woff2");
            unicode-range: U+0100-024F, U+0259, U+1E00-1EFF, U+2020, U+20A0-20AB, U+20AD-20CF, U+2113, U+2C60-2C7F, U+A720-A7FF
        }

        @font-face {
            font-family: 'Raleway';
            font-style: italic;
            font-weight: 700;
            font-display: swap;
            src: local('Raleway Bold Italic'), local(Raleway-BoldItalic), url(https://fonts.gstatic.com/s/raleway/v14/1Ptpg8zYS_SKggPNyCgw9qR_AtCb.woff2) format("woff2");
            unicode-range: U+0000-00FF, U+0131, U+0152-0153, U+02BB-02BC, U+02C6, U+02DA, U+02DC, U+2000-206F, U+2074, U+20AC, U+2122, U+2191, U+2193, U+2212, U+2215, U+FEFF, U+FFFD
        }

        @font-face {
            font-family: 'Raleway';
            font-style: normal;
            font-weight: 400;
            font-display: swap;
            src: local(Raleway), local(Raleway-Regular), url(https://fonts.gstatic.com/s/raleway/v14/1Ptug8zYS_SKggPNyCMIT5lu.woff2) format("woff2");
            unicode-range: U+0100-024F, U+0259, U+1E00-1EFF, U+2020, U+20A0-20AB, U+20AD-20CF, U+2113, U+2C60-2C7F, U+A720-A7FF
        }

        @font-face {
            font-family: 'Raleway';
            font-style: normal;
            font-weight: 400;
            font-display: swap;
            src: local(Raleway), local(Raleway-Regular), url(https://fonts.gstatic.com/s/raleway/v14/1Ptug8zYS_SKggPNyC0ITw.woff2) format("woff2");
            unicode-range: U+0000-00FF, U+0131, U+0152-0153, U+02BB-02BC, U+02C6, U+02DA, U+02DC, U+2000-206F, U+2074, U+20AC, U+2122, U+2191, U+2193, U+2212, U+2215, U+FEFF, U+FFFD
        }

        @font-face {
            font-family: 'Raleway';
            font-style: normal;
            font-weight: 500;
            font-display: swap;
            src: local('Raleway Medium'), local(Raleway-Medium), url(https://fonts.gstatic.com/s/raleway/v14/1Ptrg8zYS_SKggPNwN4rWqhPAMif.woff2) format("woff2");
            unicode-range: U+0100-024F, U+0259, U+1E00-1EFF, U+2020, U+20A0-20AB, U+20AD-20CF, U+2113, U+2C60-2C7F, U+A720-A7FF
        }

        @font-face {
            font-family: 'Raleway';
            font-style: normal;
            font-weight: 500;
            font-display: swap;
            src: local('Raleway Medium'), local(Raleway-Medium), url(https://fonts.gstatic.com/s/raleway/v14/1Ptrg8zYS_SKggPNwN4rWqZPAA.woff2) format("woff2");
            unicode-range: U+0000-00FF, U+0131, U+0152-0153, U+02BB-02BC, U+02C6, U+02DA, U+02DC, U+2000-206F, U+2074, U+20AC, U+2122, U+2191, U+2193, U+2212, U+2215, U+FEFF, U+FFFD
        }

        @font-face {
            font-family: 'Raleway';
            font-style: normal;
            font-weight: 600;
            font-display: swap;
            src: local('Raleway SemiBold'), local(Raleway-SemiBold), url(https://fonts.gstatic.com/s/raleway/v14/1Ptrg8zYS_SKggPNwPIsWqhPAMif.woff2) format("woff2");
            unicode-range: U+0100-024F, U+0259, U+1E00-1EFF, U+2020, U+20A0-20AB, U+20AD-20CF, U+2113, U+2C60-2C7F, U+A720-A7FF
        }

        @font-face {
            font-family: 'Raleway';
            font-style: normal;
            font-weight: 600;
            font-display: swap;
            src: local('Raleway SemiBold'), local(Raleway-SemiBold), url(https://fonts.gstatic.com/s/raleway/v14/1Ptrg8zYS_SKggPNwPIsWqZPAA.woff2) format("woff2");
            unicode-range: U+0000-00FF, U+0131, U+0152-0153, U+02BB-02BC, U+02C6, U+02DA, U+02DC, U+2000-206F, U+2074, U+20AC, U+2122, U+2191, U+2193, U+2212, U+2215, U+FEFF, U+FFFD
        }

        @font-face {
            font-family: 'Raleway';
            font-style: normal;
            font-weight: 700;
            font-display: swap;
            src: local('Raleway Bold'), local(Raleway-Bold), url(https://fonts.gstatic.com/s/raleway/v14/1Ptrg8zYS_SKggPNwJYtWqhPAMif.woff2) format("woff2");
            unicode-range: U+0100-024F, U+0259, U+1E00-1EFF, U+2020, U+20A0-20AB, U+20AD-20CF, U+2113, U+2C60-2C7F, U+A720-A7FF
        }

        @font-face {
            font-family: 'Raleway';
            font-style: normal;
            font-weight: 700;
            font-display: swap;
            src: local('Raleway Bold'), local(Raleway-Bold), url(https://fonts.gstatic.com/s/raleway/v14/1Ptrg8zYS_SKggPNwJYtWqZPAA.woff2) format("woff2");
            unicode-range: U+0000-00FF, U+0131, U+0152-0153, U+02BB-02BC, U+02C6, U+02DA, U+02DC, U+2000-206F, U+2074, U+20AC, U+2122, U+2191, U+2193, U+2212, U+2215, U+FEFF, U+FFFD
        }

        /*-- CSS Variables --*/

        html {
            --body-font: Josefin Sans;
            --menu-font: Josefin Sans;
            --title-font: Josefin Sans;
            --meta-font: Josefin Sans;
            --text-font: Josefin Sans;
            --body-bg-color: #6c6cfe;
            --body-bg: #6c6cfe none no-repeat scroll center center;
            --outer-bg: #ffffff;
            --main-color: #6c6cfe;
            --title-color: #ffffff;
            --title-hover-color: #6c6cfe;
            --meta-color: #a9b4ba;
            --text-color: #5b6c77;
            --tag-color: #6c6cfe;
            --header-bg: #171c24;
            --header-color: #ffffff;
            --header-hover-color: #000000;
            --submenu-bg: #ffffff;
            --submenu-color: #171c24;
            --submenu-hover-color: #000000;
            --megamenu-bg: #ffffff;
            --megamenu-color: #171c24;
            --megamenu-hover-color: #6c6cfe;
            --mobilemenu-bg: #ffffff;
            --mobilemenu-color: #171c24;
            --mobilemenu-hover-color: #6c6cfe;
            --hero-bg: #191919;
            --hero-color: #ffffff;
            --hero-text-color: #f0f0fa;
            --hero-search-color: #ffffff;
            --widget-title-color: #171c24;
            --post-title-color: #ffffff;
            --post-title-hover-color: #6c6cfe;
            --post-text-color: #5b6c77;
            --footer-bg: #1e232b;
            --footer-color: #ffffff;
            --footer-hover-color: #6c6cfe;
            --footer-post-title-color: #ffffff;
            --footer-post-title-hover-color: #6c6cfe;
            --footer-text-color: #aaaaaa;
            --footerbar-bg: #171c24;
            --footerbar-color: #ffffff;
            --footerbar-hover-color: #6c6cfe;
            --button-bg: #6c6cfe;
            --button-color: #ffffff;
            --button-hover-bg: #6161e4;
            --button-hover-color: #ffffff;
            --border-color: rgba(155, 155, 155, 0.15);
            --bb-color: rgba(0, 0, 0, 0.1);
        }

        html.rtl {
            --body-font: 'Cairo', Arial, sans-serif;
            --menu-font: 'Cairo', Arial, sans-serif;
            --title-font: 'Cairo', Arial, sans-serif;
            --meta-font: 'Cairo', Arial, sans-serif;
            --text-font: 'Cairo', Arial, sans-serif;
        }

        /*-- Reset CSS --*/

        a,
        abbr,
        acronym,
        address,
        applet,
        b,
        big,
        blockquote,
        body,
        caption,
        center,
        cite,
        code,
        dd,
        del,
        dfn,
        div,
        dl,
        dt,
        em,
        fieldset,
        font,
        form,
        h1,
        h2,
        h3,
        h4,
        h5,
        h6,
        html,
        i,
        iframe,
        img,
        ins,
        kbd,
        label,
        legend,
        li,
        object,
        p,
        pre,
        q,
        s,
        samp,
        small,
        span,
        strike,
        strong,
        sub,
        sup,
        table,
        tbody,
        td,
        tfoot,
        th,
        thead,
        tr,
        tt,
        u,
        ul,
        var {
            padding: 0;
            margin: 0;
            border: 0;
            outline: 0;
            vertical-align: baseline;
            background: 0 0;
            text-decoration: none
        }

        dl,
        ul {
            list-style-position: inside;
            list-style: none
        }

        ul li {
            list-style: none
        }

        caption {
            text-align: center
        }

        img {
            border: none;
            position: relative
        }

        a,
        a:visited {
            text-decoration: none
        }

        .clearfix {
            clear: both
        }

        .section,
        .widget,
        .widget ul {
            margin: 0;
            padding: 0
        }

        a {
            color: #8dbbff
        }

        a img {
            border: 0
        }

        abbr {
            text-decoration: none
        }

        .CSS_LIGHTBOX {
            z-index: 999999 !important
        }

        .CSS_LIGHTBOX_ATTRIBUTION_INDEX_CONTAINER .CSS_HCONT_CHILDREN_HOLDER>.CSS_LAYOUT_COMPONENT.CSS_HCONT_CHILD:first-child>.CSS_LAYOUT_COMPONENT {
            opacity: 0
        }

        .separator a {
            clear: none !important;
            float: none !important;
            margin-left: 0 !important;
            margin-right: 0 !important
        }

        #Navbar1,
        #navbar-iframe,
        .widget-item-control,
        a.quickedit,
        .home-link,
        .feed-links {
            display: none !important
        }

        .center {
            display: table;
            margin: 0 auto;
            position: relative
        }

        .widget>h2,
        .widget>h3 {
            display: none
        }

        .widget iframe,
        .widget img {
            max-width: 100%
        }

        button,
        input,
        select,
        textarea {
            font-family: var(--body-font);
            -webkit-appearance: none;
            -moz-appearance: none;
            appearance: none;
            outline: none;
            box-sizing: border-box;
            border-radius: 0
        }

        }

        .video-container {
            position: relative;
            width: 100%;
            height: 75vh;
            max-height: 500px;
            background: #000;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        video {
            width: 100%;
            height: 100%;
            object-fit: contain;
            display: block;
        }

        /*-- Style CSS --*/

        html {
            position: relative;
            text-rendering: optimizeLegibility;
            -webkit-font-smoothing: antialiased;
            margin: 0
        }

        body {
            background-color: #111;
            position: relative;
            font-family: "Poppins", sans-serif;
            font-size: 14px;
            color: var(--text-color);
            font-weight: 400;
            font-style: normal;
            line-height: 1.4em;
            word-wrap: break-word;
            margin: 0;
            padding: 0
        }

        html[data-theme=dark] body {
            background-color: var(--body-bg-color) !important
        }

        body.is-cover {
            background-attachment: fixed;
            background-size: cover;
            background-position: center center;
            background-repeat: no-repeat
        }

        .rtl {
            direction: rtl
        }

        .no-items.section {
            display: none
        }

        h1,
        h2,
        h3,
        h4,
        h5,
        h6 {
            font-weight: 600
        }

        a,
        input,
        button {
            transition: all .17s ease
        }

        #outer-wrapper {
            position: relative;
            overflow: hidden;
            width: 100%;
            max-width: 100%;
            background-color: #191919;
            margin: 0 auto;
            padding: 0;
            box-shadow: 0 0 20px rgba(0, 0, 0, .3);
            -webkit-box-shadow: 0 0 20px rgba(0, 0, 0, .3);
        }

        .is-boxed #outer-wrapper {
            width: calc(1104px + 60px);
            max-width: 100%;
        }

        .row-x1 {
            width: 1104px
        }

        #content-wrapper {
            position: relative;
            float: left;
            width: 100%;
            overflow: hidden;
            padding: 0px 0;
            margin: 0;
            border-top: 0;
            margin-top: 30px;
        }

        #content-wrapper>.container {
            margin: 0 auto
        }

        .theiaStickySidebarIfy:before,
        .theiaStickySidebarIfy:after {
            content: '';
            display: table;
            clear: both
        }

        #main-wrapper {
            position: relative;
            float: left;
            width: 100%;
            box-sizing: border-box;
            padding: 0
        }

        .is-single #main-wrapper {
            width: calc(100% - (336px + 40px))
        }

        .is-left #main-wrapper,
        .rtl #main-wrapper {
            float: right
        }

        #sidebar-wrapper {
            position: relative;
            float: right;
            width: 336px;
            box-sizing: border-box;
            padding: 0
        }

        .is-left #sidebar-wrapper,
        .rtl #sidebar-wrapper {
            float: left
        }

        .scrnsht {
            display: block;
            position: relative;
            z-index: 1;
            background: black;
            width: auto;
            bottom: -18px;
            color: chartreuse;
        }

        .post-body code {
            display: block;
            overflow-x: auto;
            padding: .5em;
            line-height: 1.3em;
            color: #abb2bf;
            background: #282c34;
            border-radius: 5px;
        }

        .node--newIndicator {
            font-size: 11px;
            color: #fefefe;
            background: #df204d;
            padding-top: 1px;
            padding-right: 7px;
            padding-bottom: 2px;
            padding-left: 4px;
            font-style: italic;
            font-weight: 600;
            text-transform: uppercase;
            clip-path: polygon(calc(10%) 0%, 100% 0%, calc(90%) 100%, 0% 100%);
        }

        .btn {
            background: #0020ff;
            color: white;
            padding: 10px 30px;
            display: inline-block;
            margin-top: 30px;
            margin-bottom: 20px;
        }

        .btn1 {
            background: #4f9a4a;
            color: white;
            padding: 10px 30px;
            display: inline-block;
            margin-top: 30px;
            margin-bottom: 20px;
        }

        .no {
            color: #fff !important;
            border: 2px solid red;
            padding-left: 20px;
            background: url() #2200ff no-repeat -1px 0;
        }

        .red {
            background: darkgray;
            color: white;
        }

        .buttn {
            line-height: 25px;
            font-size: 15px;
            font-weight: 400 700;
            font-family: Oswald;
            text-transform: uppercase;
            text-decoration: none !important;
            border-radius: 1px !important;
            padding: 10px 10px;
            margin-right: 10px;
            opacity: .96;
            -webkit-box-shadow: 4px 4px 3px 0 rgb(0 0 0 / 20%);
            -moz-box-shadow: 4px 4px 3px 0 rgba(0, 0, 0, .2);
            box-shadow: 4px 4px 3px 0 rgb(0 0 0 / 20%);
            margin-top: 20px;
            display: inline-block;
        }

        .mv_button_css {
            background: #f14e13;
            width: calc(50% - 50px);
            cursor: pointer;
            box-shadow: 0 5px 0 rgb(0 0 0 / 50%);
            display: inline-block;
            border-radius: 2px;
            margin: 15px auto;
            padding-right: 10px;
            text-decoration: none !important;
            font-weight: bold;
            color: #fff;
            display: block;
        }

        .mv_button_css:hover {
            color: #fff !important;
            background: #c73707;
        }

        .mv_button_css img {
            width: 13px;
        }

        .mv_button_css span {
            display: inline-block;
            padding: 2px 5px;
            background: rgba(0, 0, 0, 0.42);
            margin-right: 10px;
            position: relative;
        }

        .mv_button_css span:before,
        .mv_button_css span:after {
            content: &#39;
            &#39;
            ;
        }

        .mv_button_css span:after {
            left: 100%;
            top: 50%;
            border: solid transparent;
            height: 0;
            width: 0;
            position: absolute;
            pointer-events: none;
            border-color: rgba(136, 183, 213, 0);
            border-left-color: rgba(0, 0, 0, 0.42);
            border-width: 5px;
            margin-top: -5px;
        }

        .mv_button_css small {
            font-size: 11px;
        }

        @media(max-width: 480px) {
            .mv_button_css {
                width: calc(100% - 50px)
            }
        }

        #footer-tag .widget-title {
            padding: 10px;
            background: #ff4600;
            color: #e1ded5;
        }

        #footer-tag .widget-content {
            padding: 10px;
            display: -webkit-box;
            margin-top: 10px;
        }

        #footer-tag .ktag {
            text-align: center;
        }

        .tags-wrapper .widget>.widget-title {
            display: none
        }

        .tags-wrapper {
            margin: 0 auto;
        }

        .tags-wrapper .widget-content {
            position: relative;
            margin: 15px auto 0;
        }

        .tags-wrapper .menu-cat {
            text-align: center;
        }

        .tags-wrapper .menu-cat li {
            position: relative;
            display: inline-block;
            margin: 0;
        }

        .tags-wrapper .menu-cat li a {
            background-color: #df133c;
            text-transform: uppercase;
            border-radius: 15%;
            color: #fff;
            padding: 5px 5px;
            text-align: center;
            text-decoration: none;
            display: inline-block;
            font-size: 14px;
            margin: 4px 2px;
            -webkit-transition-duration: 0.4s;
            transition-duration: 0.4s;
            cursor: pointer;
            min-width: 70px;
            box-shadow: 0 0 32px -10px #fe0000;
        }

        .tags-wrapper .menu-cat li a:hover {}

        .catbox {
            display: -webkit-inline-box;
            display: flow-root;
        }

        .a2a_kit {
            -ms-touch-action: manipulation;
            touch-action: manipulation;
            outline: 0;
            background: #cccccc;
            padding: 10px;
            margin-bottom: 10px;
        }

        #blog-pager {
            clear: both;
            margin: 30px auto;
            padding: 7px;
        }

        .blog-pager {
            background: none;
        }

        .displaypageNum a,
        .showpage a,
        .pagecurrent {
            margin-right: 5px;
            color: #F4F4F4;
            background-color: #404042;
            -webkit-box-shadow: 0px 5px 3px -1px rgba(50, 50, 50, 0.53);
            -moz-box-shadow: 0px 5px 3px -1px rgba(50, 50, 50, 0.53);
            box-shadow: 0px 5px 3px -1px rgba(50, 50, 50, 0.53);
            margin-bottom: 5px;
            position: relative;
            display: inline-block;
            padding: 8px 20px;
            font-size: 15px;
            transition: all .3s;
        }

        .displaypageNum a:hover,
        .showpage a:hover,
        .pagecurrent {
            background: #EC8D04;
            text-decoration: none;
            color: #fff;
        }

        #blog-pager .showpage,
        #blog-pager,
        .pagecurrent {
            ;
            color: #000;
        }

        .showpageOf {
            display: none !important
        }

        #blog-pager .pages {
            border: none;
            -webkit-box-shadow: 0px 5px 3px -1px rgba(50, 50, 50, 0.53);
            -moz-box-shadow: 0px 5px 3px -1px rgba(50, 50, 50, 0.53);
            box-shadow: 0px 5px 3px -1px rgba(50, 50, 50, 0.53);
        }

        .entry-image-wrap,
        .cmm-avatar,
        .comments .avatar-image-container {
            overflow: hidden;
            background-color: rgba(155, 155, 155, 0.08);
            z-index: 5;
            color: transparent !important;
            transition: box-shadow .17s ease, opacity .17s ease;
        }

        html[data-theme=dark] .entry-image-wrap:hover {
            opacity: .85
        }

        .entry-thumb {
            display: block;
            position: relative;
            width: 100%;
            height: 100%;
            background-size: cover;
            background-position: center center;
            background-repeat: no-repeat;
            z-index: 1;
            opacity: 0;
            transition: opacity .35s ease, transform .35s ease
        }

        .entry-thumb.lazy-ify {
            opacity: 1
        }

        .before-mask:before {
            content: '';
            position: absolute;
            left: 0;
            right: 0;
            bottom: 0;
            height: 70%;
            background-image: linear-gradient(to bottom, transparent, rgba(0, 0, 0, 0.8));
            -webkit-backface-visibility: hidden;
            backface-visibility: hidden;
            z-index: 2;
            opacity: 1;
            margin: 0;
            transition: opacity .25s ease
        }

        .entry-image-wrap.is-video:after {
            position: absolute;
            content: '\f04b';
            top: 50%;
            left: 50%;
            background-color: rgba(0, 0, 0, 0.5);
            width: 44px;
            height: 30px;
            font-family: 'Font Awesome 5 Free';
            font-size: 12px;
            color: #fff;
            font-weight: 900;
            text-align: center;
            line-height: 30px;
            z-index: 5;
            transform: translate(-50%, -50%);
            box-sizing: border-box;
            margin: 0;
            border-radius: 6px;
            transition: background .17s ease
        }

        .entry-image-wrap.is-video:hover:after,
        .featured-item-inner:hover .entry-image-wrap.is-video:after {
            background-color: var(--main-color)
        }

        .entry-meta {
            float: left;
            width: 100%;
            font-family: var(--meta-font);
            font-size: 13px;
            color: #7e7e7e;
            font-weight: 400;
            line-height: 16px;
            margin: 0
        }

        .rtl .entry-meta .m-item {
            float: right
        }

        .entry-category {
            display: none !important;
            position: relative;
            font-size: 12px;
            color: #228b22;
            font-weight: 600;
            text-transform: uppercase;
            z-index: 10;
            margin: 0 0 6px
        }

        .entry-title {
            color: #fff;
            font-weight: 400;
            line-height: 1.3em
        }

        .entry-title a {
            display: block;
            color: #fff
        }

        .entry-title a:hover {
            color: var(--post-title-hover-color)
        }

        .excerpt {
            font-family: var(--text-font);
            line-height: 1.5em
        }

        .entry-info {
            position: absolute;
            left: 0;
            bottom: 0;
            width: 100%;
            background: linear-gradient(to bottom, transparent, rgba(0, 0, 0, 0.8));
            overflow: hidden;
            z-index: 10;
            box-sizing: border-box;
            padding: 15px
        }

        .entry-info .entry-title {
            text-shadow: 0 1px 2px rgba(0, 0, 0, 0.5)
        }

        .entry-info .entry-title a {
            color: #fff
        }

        .error-msg {
            display: block;
            font-size: 14px;
            color: var(--text-color);
            padding: 30px 0;
            font-weight: 400
        }

        .error-msg b {
            font-weight: 700
        }

        .social a:before {
            display: inline-block;
            font-family: 'Font Awesome 5 Brands';
            font-style: normal;
            font-weight: 400
        }

        .social .blogger a:before {
            content: '\f37d'
        }

        .social .facebook a:before {
            content: '\f09a'
        }

        .social .facebook-f a:before {
            content: '\f39e'
        }

        .social .twitter a:before {
            content: '\f099'
        }

        .social .rss a:before {
            content: '\f09e';
            font-family: 'Font Awesome 5 Free';
            font-weight: 900
        }

        .social .youtube a:before {
            content: '\f167'
        }

        .social .skype a:before {
            content: '\f17e'
        }

        .social .stumbleupon a:before {
            content: '\f1a4'
        }

        .social .tumblr a:before {
            content: '\f173'
        }

        .social .vk a:before {
            content: '\f189'
        }

        .social .stack-overflow a:before {
            content: '\f16c'
        }

        .social .github a:before {
            content: '\f09b'
        }

        .social .linkedin a:before {
            content: '\f0e1'
        }

        .social .dribbble a:before {
            content: '\f17d'
        }

        .social .soundcloud a:before {
            content: '\f1be'
        }

        .social .behance a:before {
            content: '\f1b4'
        }

        .social .digg a:before {
            content: '\f1a6'
        }

        .social .instagram a:before {
            content: '\f16d'
        }

        .social .pinterest a:before {
            content: '\f0d2'
        }

        .social .pinterest-p a:before {
            content: '\f231'
        }

        .social .twitch a:before {
            content: '\f1e8'
        }

        .social .delicious a:before {
            content: '\f1a5'
        }

        .social .codepen a:before {
            content: '\f1cb'
        }

        .social .flipboard a:before {
            content: '\f44d'
        }

        .social .reddit a:before {
            content: '\f281'
        }

        .social .whatsapp a:before {
            content: '\f232'
        }

        .social .messenger a:before {
            content: '\f39f'
        }

        .social .snapchat a:before {
            content: '\f2ac'
        }

        .social .telegram a:before {
            content: '\f3fe'
        }

        .social .discord a:before {
            content: '\f392'
        }

        .social .share a:before {
            content: '\f064';
            font-family: 'Font Awesome 5 Free';
            font-weight: 900
        }

        .social .email a:before {
            content: '\f0e0';
            font-family: 'Font Awesome 5 Free'
        }

        .social .external-link a:before {
            content: '\f35d';
            font-family: 'Font Awesome 5 Free';
            font-weight: 900
        }

        .social-bg .blogger a,
        .social-bg-hover .blogger a:hover {
            background-color: #f30
        }

        .social-bg .facebook a,
        .social-bg .facebook-f a,
        .social-bg-hover .facebook a:hover,
        .social-bg-hover .facebook-f a:hover {
            background-color: #3b5999
        }

        .social-bg .twitter a,
        .social-bg-hover .twitter a:hover {
            background-color: #00acee
        }

        .social-bg .youtube a,
        .social-bg-hover .youtube a:hover {
            background-color: #f50000
        }

        .social-bg .instagram a,
        .social-bg-hover .instagram a:hover {
            background: linear-gradient(15deg, #ffb13d, #dd277b, #4d5ed4)
        }

        .social-bg .pinterest a,
        .social-bg .pinterest-p a,
        .social-bg-hover .pinterest a:hover,
        .social-bg-hover .pinterest-p a:hover {
            background-color: #ca2127
        }

        .social-bg .dribbble a,
        .social-bg-hover .dribbble a:hover {
            background-color: #ea4c89
        }

        .social-bg .linkedin a,
        .social-bg-hover .linkedin a:hover {
            background-color: #0077b5
        }

        .social-bg .tumblr a,
        .social-bg-hover .tumblr a:hover {
            background-color: #365069
        }

        .social-bg .twitch a,
        .social-bg-hover .twitch a:hover {
            background-color: #6441a5
        }

        .social-bg .rss a,
        .social-bg-hover .rss a:hover {
            background-color: #ffc200
        }

        .social-bg .skype a,
        .social-bg-hover .skype a:hover {
            background-color: #00aff0
        }

        .social-bg .stumbleupon a,
        .social-bg-hover .stumbleupon a:hover {
            background-color: #eb4823
        }

        .social-bg .vk a,
        .social-bg-hover .vk a:hover {
            background-color: #4a76a8
        }

        .social-bg .stack-overflow a,
        .social-bg-hover .stack-overflow a:hover {
            background-color: #f48024
        }

        .social-bg .github a,
        .social-bg-hover .github a:hover {
            background-color: #24292e
        }

        .social-bg .soundcloud a,
        .social-bg-hover .soundcloud a:hover {
            background: linear-gradient(#ff7400, #ff3400)
        }

        .social-bg .behance a,
        .social-bg-hover .behance a:hover {
            background-color: #191919
        }

        .social-bg .digg a,
        .social-bg-hover .digg a:hover {
            background-color: #1b1a19
        }

        .social-bg .delicious a,
        .social-bg-hover .delicious a:hover {
            background-color: #0076e8
        }

        .social-bg .codepen a,
        .social-bg-hover .codepen a:hover {
            background-color: #000
        }

        .social-bg .flipboard a,
        .social-bg-hover .flipboard a:hover {
            background-color: #f52828
        }

        .social-bg .reddit a,
        .social-bg-hover .reddit a:hover {
            background-color: #ff4500
        }

        .social-bg .whatsapp a,
        .social-bg-hover .whatsapp a:hover {
            background-color: #3fbb50
        }

        .social-bg .messenger a,
        .social-bg-hover .messenger a:hover {
            background-color: #0084ff
        }

        .social-bg .snapchat a,
        .social-bg-hover .snapchat a:hover {
            background-color: #ffe700
        }

        .social-bg .telegram a,
        .social-bg-hover .telegram a:hover {
            background-color: #179cde
        }

        .social-bg .discord a,
        .social-bg-hover .discord a:hover {
            background-color: #7289da
        }

        .social-bg .share a,
        .social-bg-hover .share a:hover {
            background-color: var(--meta-color)
        }

        .social-bg .email a,
        .social-bg-hover .email a:hover {
            background-color: #888
        }

        .social-bg .external-link a,
        .social-bg-hover .external-link a:hover {
            background-color: var(--button-hover-bg)
        }

        .social-color .blogger a,
        .social-color-hover .blogger a:hover {
            color: #f30
        }

        .social-color .facebook a,
        .social-color .facebook-f a,
        .social-color-hover .facebook a:hover,
        .social-color-hover .facebook-f a:hover {
            color: #3b5999
        }

        .social-color .twitter a,
        .social-color-hover .twitter a:hover {
            color: #00acee
        }

        .social-color .youtube a,
        .social-color-hover .youtube a:hover {
            color: #f50000
        }

        .social-color .instagram a,
        .social-color-hover .instagram a:hover {
            color: #dd277b
        }

        .social-color .pinterest a,
        .social-color .pinterest-p a,
        .social-color-hover .pinterest a:hover,
        .social-color-hover .pinterest-p a:hover {
            color: #ca2127
        }

        .social-color .dribbble a,
        .social-color-hover .dribbble a:hover {
            color: #ea4c89
        }

        .social-color .linkedin a,
        .social-color-hover .linkedin a:hover {
            color: #0077b5
        }

        .social-color .tumblr a,
        .social-color-hover .tumblr a:hover {
            color: #365069
        }

        .social-color .twitch a,
        .social-color-hover .twitch a:hover {
            color: #6441a5
        }

        .social-color .rss a,
        .social-color-hover .rss a:hover {
            color: #ffc200
        }

        .social-color .skype a,
        .social-color-hover .skype a:hover {
            color: #00aff0
        }

        .social-color .stumbleupon a,
        .social-color-hover .stumbleupon a:hover {
            color: #eb4823
        }

        .social-color .vk a,
        .social-color-hover .vk a:hover {
            color: #4a76a8
        }

        .social-color .stack-overflow a,
        .social-color-hover .stack-overflow a:hover {
            color: #f48024
        }

        .social-color .github a,
        .social-color-hover .github a:hover {
            color: #24292e
        }

        .social-color .soundcloud a,
        .social-color-hover .soundcloud a:hover {
            color: #ff7400
        }

        .social-color .behance a,
        .social-color-hover .behance a:hover {
            color: #191919
        }

        .social-color .digg a,
        .social-color-hover .digg a:hover {
            color: #1b1a19
        }

        .social-color .delicious a,
        .social-color-hover .delicious a:hover {
            color: #0076e8
        }

        .social-color .codepen a,
        .social-color-hover .codepen a:hover {
            color: #000
        }

        .social-color .flipboard a,
        .social-color-hover .flipboard a:hover {
            color: #f52828
        }

        .social-color .reddit a,
        .social-color-hover .reddit a:hover {
            color: #ff4500
        }

        .social-color .whatsapp a,
        .social-color-hover .whatsapp a:hover {
            color: #3fbb50
        }

        .social-color .messenger a,
        .social-color-hover .messenger a:hover {
            color: #0084ff
        }

        .social-color .snapchat a,
        .social-color-hover .snapchat a:hover {
            color: #ffe700
        }

        .social-color .telegram a,
        .social-color-hover .telegram a:hover {
            color: #179cde
        }

        .social-color .discord a,
        .social-color-hover .discord a:hover {
            color: #7289da
        }

        .social-color .share a,
        .social-color-hover .share a:hover {
            color: var(--meta-color)
        }

        .social-color .email a,
        .social-color-hover .email a:hover {
            color: #888
        }

        .social-color .external-link a,
        .social-color-hover .external-link a:hover {
            color: var(--button-hover-bg)
        }

        #freebify-free-header-wrapper {
            position: relative;
            float: left;
            width: 100%;
            margin: 0;
            background: #080808;
        }

        #freebify-free-header-wrapper .container {
            position: relative;
            margin: 0 auto
        }

        .headerify-wrap,
        .headerify {
            position: relative;
            float: left;
            width: 100%;
            height: auto;
            z-index: 50;
            box-sizing: border-box;
            padding: 0;
            margin: 0
        }

        .headerify-inner {
            position: relative;
            float: left;
            width: 100%;
            height: auto background-color: #ffffff;
            border-top: 3px solid #080808;
            border-bottom: 3px solid #080808;
            box-sizing: border-box;
            padding: 0;
            margin: 0;
            box-shadow: 0 1px 5px 0 rgba(0, 0, 0, 0.1);
        }

        .is-boxed .headerify-inner {
            float: none;
            width: calc(1104px + 60px);
            max-width: 100%;
            margin: 0 auto;
            border: 0
        }

        .headerify-items {
            position: relative;
            float: left;
            width: 100%;
            height: auto;
            box-sizing: border-box;
            margin: 0;
        }

        . . #header-ads-wrap {
            display: none;
            position: relative;
            float: left;
            width: 100%;
            z-index: 10;
            margin: 0;
            border-bottom: 1px solid var(--border-color)
        }

        #header-ads-wrap.has-widget {
            display: block
        }

        #header-ads-wrap .container {
            margin: 0 auto
        }

        .header-ads .widget {
            position: relative;
            float: left;
            width: 100%;
            text-align: center;
            line-height: 0;
            margin: 20px 0
        }

        .is-post #header-ads-wrap .widget {
            margin: 20px 0
        }

        .header-ads .widget-content {
            float: left;
            width: 100%;
            margin: 0
        }

        .header-ads .widget>.widget-title {
            display: none
        }

        .loader {
            position: relative;
            height: 100%;
            overflow: hidden;
            display: block;
            margin: 0
        }

        .loader:after {
            content: '';
            position: absolute;
            top: 50%;
            left: 50%;
            width: 28px;
            height: 28px;
            margin: -16px 0 0 -16px;
            border: 2px solid var(--main-color);
            border-right-color: var(--border-color);
            border-radius: 100%;
            animation: spinner .65s infinite linear;
            transform-origin: center
        }

        @-webkit-keyframes spinner {
            0% {
                -webkit-transform: rotate(0deg);
                transform: rotate(0deg)
            }
            to {
                -webkit-transform: rotate(1turn);
                transform: rotate(1turn)
            }
        }

        @keyframes spinner {
            0% {
                -webkit-transform: rotate(0deg);
                transform: rotate(0deg)
            }
            to {
                -webkit-transform: rotate(1turn);
                transform: rotate(1turn)
            }
        }

        #featured-wrapper {
            position: relative;
            float: left;
            width: 100%;
            margin: 0;
            border-bottom: 1px solid var(--border-color)
        }

        #featured-wrapper .container {
            margin: 0 auto
        }

        #featured .widget,
        #featured .widget>.widget-title {
            display: none
        }

        #featured .widget.FeaturedPost {
            display: block;
            position: relative;
            float: left;
            width: 100%;
            margin: 35px 0
        }

        #featured .widget-content {
            position: relative;
            float: left;
            width: 100%;
            margin: 0
        }

        .FeaturedPost .big-featured-post {
            position: relative;
            float: left;
            width: 100%;
            margin: 0
        }

        .FeaturedPost .big-featured-post .entry-image-wrap {
            position: relative;
            float: left;
            width: calc((100% / 2) - 15px);
            height: 320px;
            z-index: 1;
            overflow: hidden;
            margin: 0 30px 0 0;
            border-radius: 6px
        }

        .rtl .FeaturedPost .big-featured-post .entry-image-wrap {
            float: right;
            margin: 0 0 0 30px
        }

        .FeaturedPost .big-featured-post .entry-image-wrap.is-video:after {
            width: 56px;
            height: 36px;
            line-height: 36px;
            font-size: 14px;
            border-radius: 8px
        }

        .FeaturedPost .big-featured-post .entry-header {
            display: table;
            padding: 15px 0 0
        }

        .FeaturedPost .big-featured-post .entry-meta {
            font-size: 13px;
            line-height: 1;
            margin: 0 0 13px
        }

        .FeaturedPost .big-featured-post .entry-category,
        .FeaturedPost .big-featured-post .t-label {
            margin: 0 3px 0 0
        }

        .rtl .FeaturedPost .big-featured-post .entry-category,
        .rtl .FeaturedPost .big-featured-post .t-label {
            margin: 0 0 0 3px
        }

        .FeaturedPost .big-featured-post .entry-category {
            font-size: 13px
        }

        .FeaturedPost .big-featured-post .entry-title {
            float: left;
            width: 100%;
            font-size: 30px;
            margin: 0
        }

        .FeaturedPost .big-featured-post .entry-excerpt {
            float: left;
            width: 100%;
            font-size: 14px;
            margin: 13px 0 0
        }

        .FeaturedPost .big-featured-post a.read-more {
            display: inline-block;
            height: 36px;
            background-color: var(--button-bg);
            font-size: 14px;
            color: var(--button-color);
            font-weight: 500;
            line-height: 36px;
            box-sizing: border-box;
            padding: 0 25px;
            margin: 23px 0 0;
            border-bottom: 2px solid var(--bb-color);
            border-radius: 6px
        }

        .FeaturedPost .big-featured-post a.read-more:hover {
            background-color: var(--button-hover-bg);
            color: var(--button-hover-color)
        }

        .FeaturedPost .big-featured-post .entry-image-wrap.is-video:after {
            width: 56px;
            height: 36px;
            line-height: 36px;
            font-size: 14px;
            border-radius: 8px
        }

        #main-wrapper #main {
            position: relative;
            float: left;
            width: 100%;
            box-sizing: border-box;
            margin: 0
        }

        .is-home #main-wrapper.main-margin #main {
            margin-bottom: 30px
        }

        #main .Blog {
            display: flex;
            flex-wrap: wrap;
            flex-direction: column;
            margin: 0
        }

        .queryMessage {
            float: left;
            width: 100%;
            color: var(--title-color);
            margin: 0 0 20px;
            text-align: center;
            border-bottom: 1px dotted #ccc;
            padding: 10px;
        }

        .queryMessage .query-info,
        .Blog.no-posts .queryMessage {
            margin: 0
        }

        .queryMessage .query-info {
            font-size: 16px;
            color: var(--title-color);
            font-weight: 500;
            text-transform: uppercase;
            line-height: 1;
            letter-spacing: 1px;
            margin: 0
        }

        .queryMessage .query-label:after {
            content: '\f078';
            display: inline-block;
            vertical-align: middle;
            font-family: 'Font Awesome 5 Free';
            font-size: 12px;
            font-weight: 900;
            margin: 0 0 0 3px
        }

        .rtl .queryMessage .query-label:after {
            margin: 0 3px 0 0
        }

        .queryEmpty {
            font-size: 14px;
            font-weight: 400;
            padding: 0;
            margin: 40px 0;
            text-align: center
        }

        .blog-post {
            display: block;
            word-wrap: break-word
        }

        .title-wrap {
            position: relative;
            float: left;
            width: 100%;
            box-sizing: border-box;
            margin: 0 0 20px;
            background: #000000;
            padding: 10px;
        }

        .title-wrap>h3 {
            position: relative;
            float: left;
            font-family: var(--title-font);
            font-size: 18px;
            color: white;
            font-weight: 500;
            text-transform: uppercase;
            line-height: 1;
            letter-spacing: 1px;
            padding: 0;
            margin: 0
        }

        .rtl .title-wrap>h3 {
            float: right
        }

        .index-post-wrap {
            position: relative;
            display: flex;
            flex-wrap: wrap;
            box-sizing: border-box;
            padding: 0;
            margin: 0 -15px
        }

        .Blog.no-posts .index-post-wrap {
            display: none
        }

        .post-animated {
            -webkit-animation-duration: .5s;
            animation-duration: .5s;
            -webkit-animation-fill-mode: both;
            animation-fill-mode: both
        }

        @keyframes fadeIn {
            from {
                opacity: 0
            }
            to {
                opacity: 1
            }
        }

        .post-fadeIn {
            animation-name: fadeIn
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translate3d(0, 5px, 0)
            }
            to {
                opacity: 1;
                transform: translate3d(0, 0, 0)
            }
        }

        .post-fadeInUp {
            animation-name: fadeInUp
        }

        .index-post.post-ad-type {
            padding: 0 15px !important;
            margin: 0 0 35px !important;
            border-width: 0 !important
        }

        .index-post .entry-image-wrap {
            position: relative;
            float: left;
            width: 100%;
            height: 250px;
            overflow: hidden;
            margin: 0 0 12px;
            border-radius: 0px;
            box-shadow: none;
            background: linear-gradient(#222, #222), linear-gradient(to right, #ca4747, #f4c922);
            background-repeat: repeat, repeat;
            background-origin: padding-box, padding-box;
            background-origin: padding-box, border-box;
            background-repeat: no-repeat;
            border: 5px solid transparent;
        }

        .index-post .entry-header {
            float: left;
            width: 100%;
            margin: 0;
            padding-bottom: 10px;
        }

        .index-post .entry-meta {
            font-size: 14px;
            line-height: 1;
            margin: 0 0 6px;
            text-align: center;
        }

        .index-post .entry-category,
        .index-post .entry-meta .t-label {
            margin: 0 3px 0 0
        }

        .rtl .index-post .entry-category,
        .rtl .index-post .entry-meta .t-label {
            margin: 0 0 0 3px
        }

        .index-post .entry-category {
            font-size: 14px;
            display: block;
        }

        .index-post .entry-title {
            width: 100%;
            font-size: 16px;
            margin: 0
        }

        .inline-ad-wrap {
            position: relative;
            float: left;
            width: 100%;
            margin: 0
        }

        .inline-ad {
            position: relative;
            float: left;
            width: 100%;
            text-align: center;
            line-height: 1;
            margin: 0
        }

        .item-post-wrap,
        .is-single .item-post,
        .item-post-inner {
            position: relative;
            float: left;
            width: 100%;
            margin: 0
        }

        .item-post .blog-entry-header {
            position: relative;
            float: left;
            width: 100%;
            box-sizing: border-box;
            padding: 0;
            margin: 0
        }

        #breadcrumb {
            float: left;
            width: 100%;
            font-family: var(--meta-font);
            font-size: 13px;
            color: var(--meta-color);
            font-weight: 400;
            line-height: 1;
            margin: 0 0 12px
        }

        #breadcrumb a {
            color: var(--meta-color)
        }

        #breadcrumb a.home,
        #breadcrumb a:hover {
            color: var(--main-color)
        }

        #breadcrumb a,
        #breadcrumb em {
            display: inline-block
        }

        #breadcrumb em:after {
            content: '\f054';
            font-family: 'Font Awesome 5 Free';
            font-size: 9px;
            font-weight: 900;
            font-style: normal;
            margin: 0 3px
        }

        .rtl #breadcrumb em:after {
            content: '\f053'
        }

        .item-post h1.entry-title {
            position: relative;
            float: left;
            width: 100%;
            font-weight: 700;
            margin: 0;
            color: #fff;
            font-size: 25px;
            font-weight: 700;
            word-wrap: break-word;
        }

        .item-post .has-meta h1.entry-title {
            margin-bottom: 20px
        }

        .item-post .entry-meta.has-author {
            line-height: 30px
        }

        .item-post .entry-meta .author-avatar {
            position: relative;
            width: 30px;
            height: 30px;
            background-color: rgba(155, 155, 155, 0.08);
            background-size: 100%;
            margin: 0 5px 0 0;
            border-radius: 50%;
            box-shadow: 0 1px 2px rgba(155, 155, 155, .15)
        }

        .rtl .item-post .entry-meta .author-avatar {
            margin: 0 0 0 5px
        }

        .item-post .entry-meta .a-label {
            margin: 0 5px 0 0
        }

        .rtl .item-post .entry-meta .a-label {
            margin: 0 0 0 5px
        }

        .item-post .entry-meta .author-name {
            color: var(--main-color);
            font-weight: 600;
            margin: 0
        }

        .item-post .entry-meta .entry-time span {
            margin: 0 5px
        }

        .item-post .entry-meta .entry-comments-link {
            display: none;
            float: right;
            margin: 0 0 0 12px
        }

        .item-post .entry-meta .entry-comments-link:before {
            color: var(--main-color)
        }

        .rtl .item-post .entry-meta .entry-comments-link {
            float: left;
            margin: 0 12px 0 0
        }

        .item-post .entry-meta .entry-comments-link:before {
            display: inline-block;
            vertical-align: middle;
            content: '\f086';
            font-family: 'Font Awesome 5 Free';
            font-size: 13px;
            font-weight: 400;
            margin: 0 5px 0 0
        }

        .rtl .item-post .entry-meta .entry-comments-link:before {
            margin: 0 0 0 5px
        }

        .item-post .entry-meta .entry-comments-link.show {
            display: block
        }

        .entry-content-wrap {
            position: relative;
            float: left;
            width: 100%;
            box-sizing: border-box;
            margin: 0;
            line-height: 35px;
            margin-bottom: 30px;
            text-align: left;
            word-wrap: break-word;
        }

        #post-body {
            position: relative;
            float: left;
            width: 100%;
            font-size: 15px;
            color: #dddddd;
            line-height: 35px;
            padding: 0;
            margin: 25px 0 0;
        }

        #post-body b {
            color: #ff5353;
        }

        .post-body h1,
        .post-body h2,
        .post-body h3,
        .post-body h4,
        .post-body h5,
        .post-body h6 {
            font-size: 18px;
            color: var(--post-title-color);
            margin: 15px 0 15px
        }

        .post-body h1,
        .post-body h2 {
            font-size: 27px
        }

        .post-body h3 {
            font-size: 23px
        }

        blockquote {
            display: inline-block;
            background-color: #404040;
            /* position: relative; */
            color: #ffffff;
            font-style: normal;
            padding: 0px 20px;
            margin: 10px;
            border-left: 10px solid #ffc83d;
            border-radius: 6px;
            font-size: 18px;
            width: fit-content;
        }

        }

        #sidebar-wrapper .sidebar>.widget:last-child {
            margin: 0
        }

        .sidebar .widget-content {
            float: left;
            width: 100%;
            box-sizing: border-box;
            padding: 0 15px;
            margin: 0
        }

        .sidebar>.widget.no-style>.widget-title {
            display: none
        }

        .sidebar ul.social-icons {
            display: flex;
            flex-wrap: wrap;
            margin: 0
        }

        .sidebar .social-icons li {
            float: left;
            width: 100%;
            box-sizing: border-box;
            padding: 0;
            margin: 10px 0 0
        }

        .sidebar .social-icons li.link-0 {
            margin: 0
        }

        .sidebar .social-icons li a {
            position: relative;
            float: left;
            width: 100%;
            height: 40px;
            overflow: hidden;
            font-size: 14px;
            color: #fff;
            text-align: center;
            line-height: 40px;
            box-sizing: border-box;
            padding: 0;
            border-bottom: 2px solid var(--bb-color);
            border-radius: 6px
        }

        .sidebar .social-icons li a.instagram {
            border: 0;
            box-shadow: inset 0 -2px 0 0 var(--bb-color)
        }

        .sidebar .social-icons li a:before {
            float: right;
            position: absolute;
            left: 0;
            font-size: 50px;
            padding: 0 15px;
            margin: 0;
            opacity: .13;
            transform: rotate(15deg)
        }

        .rtl .sidebar .social-icons li a:before {
            left: unset;
            right: 0;
            transform: rotate(-15deg)
        }

        .sidebar .social-icons li a span {
            display: block;
            font-weight: 500;
            padding: 0
        }

        .sidebar .social-icons li a:hover {
            opacity: .85
        }

        .sidebar .loader {
            height: 180px
        }

        .list1-items .list1-item {
            float: left;
            width: 100%;
            padding: 0;
            margin: 20px 0 0
        }

        .list1-items .list1-item.item-0 {
            margin: 0
        }

        .list1-items .entry-image-wrap {
            position: relative;
            float: left;
            width: 96px;
            height: 64px;
            overflow: hidden;
            margin: 0 13px 0 0;
            border-radius: 6px
        }

        .list1-items .entry-image-wrap.is-video:after {
            width: 32px;
            height: 22px;
            line-height: 22px;
            font-size: 8px;
            border-radius: 4px
        }

        .rtl .list1-items .entry-image-wrap {
            float: right;
            margin: 0 0 0 13px
        }

        .list1-items .cmm-avatar {
            width: 55px;
            height: 55px
        }

        .list1-items .entry-header {
            overflow: hidden
        }

        .list1-items .entry-title {
            font-size: 15px;
            margin: 0
        }

        .list1-items .cmm-snippet {
            font-size: 12px;
            margin: 4px 0 0
        }

        .PopularPosts .popular-post {
            float: left;
            width: 100%;
            padding: 0;
            margin: 25px 0 0
        }

        .PopularPosts .popular-post.item-0 {
            margin: 0
        }

        .PopularPosts .entry-image-wrap {
            position: relative;
            float: left;
            width: 96px;
            height: 64px;
            overflow: hidden;
            z-index: 1;
            margin: 0 13px 0 0;
            border-radius: 6px
        }

        .PopularPosts .big-popular .entry-image-wrap {
            width: 100%;
            height: 175px;
            margin: 0 0 13px
        }

        .rtl .PopularPosts .post:not(.big-popular) .entry-image-wrap {
            float: right;
            margin: 0 0 0 13px
        }

        .PopularPosts .post:not(.big-popular) .entry-image-wrap.is-video:after {
            width: 32px;
            height: 22px;
            line-height: 22px;
            font-size: 8px;
            border-radius: 6px
        }

        .PopularPosts .post:not(.big-popular) .entry-header {
            overflow: hidden
        }

        .PopularPosts .big-popular .entry-header {
            float: left;
            width: 100%;
            margin: 0
        }

        .PopularPosts .entry-meta {
            font-size: 12px;
            line-height: 1;
            margin: 0 0 6px
        }

        .PopularPosts .entry-category,
        .PopularPosts .entry-meta .t-label {
            margin: 0 3px 0 0
        }

        .rtl .PopularPosts .entry-category,
        .rtl .PopularPosts .entry-meta .t-label {
            margin: 0 0 0 3px
        }

        .PopularPosts .entry-category {
            font-size: 12px
        }

        .PopularPosts .entry-title {
            font-size: 15px;
            margin: 0
        }

        .PopularPosts .big-popular .entry-title {
            float: left;
            width: 100%;
            font-size: 18px;
            margin: 0
        }

        .FeaturedPost .featured-post .entry-image-wrap {
            position: relative;
            float: left;
            width: 100%;
            height: 175px;
            z-index: 1;
            overflow: hidden;
            margin: 0 0 13px;
            border-radius: 6px
        }

        .FeaturedPost .featured-post .entry-meta {
            font-size: 12px;
            line-height: 1;
            margin: 0 0 6px
        }

        .FeaturedPost .featured-post .entry-category {
            font-size: 12px
        }

        .FeaturedPost .featured-post .entry-category,
        .FeaturedPost .featured-post .entry-meta .t-label {
            margin: 0 3px 0 0
        }

        .rtl .FeaturedPost .featured-post .entry-category,
        .rtl .FeaturedPost .featured-post .entry-meta .t-label {
            margin: 0 0 0 3px
        }

        .FeaturedPost .featured-post .entry-title {
            float: left;
            width: 100%;
            font-size: 18px;
            margin: 0
        }

        #sidebar-wrapper .sidebar>.widget.FollowByEmail {
            margin-top: 10px
        }

        .follow-by-email-content {
            position: relative;
            float: left;
            width: 100%;
            background-color: rgba(155, 155, 155, 0.08);
            box-sizing: border-box;
            padding: 20px;
            border: 0;
            border-radius: 6px
        }

        .follow-by-email-content:before {
            content: '\f0e0';
            position: absolute;
            top: 0;
            left: 50%;
            width: 36px;
            height: 36px;
            background-color: var(--button-bg);
            font-family: 'Font Awesome 5 Free';
            font-size: 18px;
            color: var(--button-color);
            line-height: 36px;
            text-align: center;
            transform: translate(-50%, -30%);
            margin: 0;
            border-radius: 50%
        }

        .follow-by-email-title {
            display: block;
            font-family: var(--title-font);
            font-size: 21px;
            color: var(--title-color);
            font-weight: 600;
            line-height: 1.2em;
            text-align: center;
            padding: 20px 15px;
            margin: 0
        }

        .follow-by-email-address {
            width: 100%;
            height: 36px;
            background-color: rgba(0, 0, 0, 0.03);
            font-family: inherit;
            font-size: 13px;
            color: var(--text-color);
            text-align: center;
            box-sizing: border-box;
            padding: 0 10px;
            margin: 0 0 10px;
            border: 1px solid var(--border-color);
            border-radius: 6px
        }

        html[data-theme=dark] .follow-by-email-address {
            background-color: rgba(255, 255, 255, 0.03)
        }

        .follow-by-email-address:focus {
            background-color: var(--outer-bg) !important;
            border-color: var(--border-color) !important
        }

        .follow-by-email-submit {
            width: 100%;
            height: 36px;
            background-color: var(--button-bg);
            font-family: inherit;
            font-size: 14px;
            color: var(--button-color);
            font-weight: 500;
            line-height: 36px;
            cursor: pointer;
            padding: 0 20px;
            border: 0;
            border-bottom: 2px solid var(--bb-color);
            border-radius: 6px
        }

        .follow-by-email-submit:hover {
            background-color: var(--button-hover-bg);
            color: var(--button-hover-color)
        }

        .follow-by-email-text {
            display: block;
            font-size: 12px;
            color: var(--text-color);
            text-align: center;
            font-style: italic;
            margin: 8px 0 0
        }

        #freebify-free-post-newsletter .widget-content-inner {
            position: relative;
            float: left;
            width: 100%;
            background-color: var(--border-color);
            box-sizing: border-box;
            padding: 8px;
            border-radius: 6px
        }

        #freebify-free-post-newsletter .follow-by-email-content {
            background-color: var(--outer-bg);
            box-shadow: 0 1px 2px rgba(155, 155, 155, .15)
        }

        #freebify-free-post-newsletter .follow-by-email-content:before {
            transform: translate(-50%, -50%);
            margin: 0
        }

        .list-label li,
        .archive-list li {
            position: relative;
            display: block
        }

        .list-label li a,
        .archive-list li a {
            display: block;
            color: var(--title-color);
            font-size: 14px;
            font-weight: 400;
            padding: 5px 0
        }

        .archive-list li a {
            text-transform: capitalize
        }

        .list-label li:first-child a,
        .archive-list li:first-child a {
            padding: 0 0 5px
        }

        .list-label li:last-child a,
        .archive-list li:last-child a {
            padding-bottom: 0
        }

        .list-label li a:before,
        .archive-list li a:before {
            content: '\f054';
            font-family: 'Font Awesome 5 Free';
            float: left;
            font-size: 7px;
            font-weight: 900;
            font-style: normal;
            margin: 1px 3px 0 0
        }

        .rtl .list-label li a:before,
        .rtl .archive-list li a:before {
            content: '\f053';
            float: right;
            margin: 1px 0 0 3px
        }

        .list-label li a:hover,
        .archive-list li a:hover {
            color: var(--title-hover-color)
        }

        .list-label .label-count,
        .archive-list .archive-count {
            float: right;
            font-size: 12px;
            color: var(--meta-color);
            text-decoration: none;
            margin: 1px 0 0 5px
        }

        .rtl .list-label .label-count,
        .rtl .archive-list .archive-count {
            float: left;
            margin: 1px 5px 0 0
        }

        .cloud-label li {
            position: relative;
            float: left;
            margin: 0 5px 5px 0
        }

        .rtl .cloud-label li {
            float: right;
            margin: 0 0 5px 5px
        }

        .cloud-label li a {
            display: block;
            height: 28px;
            background-color: rgb(155 155 155 / 78%);
            color: #000000;
            font-size: 13px;
            line-height: 28px;
            font-weight: 400;
            box-sizing: border-box;
            padding: 0 13px;
            border-bottom: 2px solid var(--bb-color);
            border-radius: 6px
        }

        .cloud-label li a:hover {
            background-color: var(--button-hover-bg);
            color: var(--button-hover-color)
        }

        .cloud-label .label-count {
            display: none
        }

        .search-widget .search-form {
            position: relative;
            float: left;
            width: 100%;
            margin: 0
        }

        .search-widget .search-input {
            float: left;
            width: 100%;
            height: 36px;
            background-color: rgba(255, 255, 255, 0);
            font-family: inherit;
            font-weight: 400;
            font-size: 14px;
            color: var(--text-color);
            line-height: 36px;
            box-sizing: border-box;
            padding: 0 15px;
            margin: 0;
            border: 1px solid var(--border-color);
            border-radius: 6px
        }

        .search-widget .search-input:focus {
            outline: none;
            background-color: rgba(0, 0, 0, 0.03)
        }

        .search-widget .search-action {
            position: absolute;
            top: 0;
            right: 0;
            height: 30px;
            font-family: inherit;
            font-size: 14px;
            font-weight: 400;
            line-height: 30px;
            cursor: pointer;
            box-sizing: border-box;
            background-color: var(--button-bg);
            color: var(--button-color);
            padding: 0 15px;
            margin: 3px 3px 0 0;
            border: 0;
            border-bottom: 2px solid var(--bb-color);
            border-radius: 6px
        }

        .search-widget .search-action:hover {
            background-color: var(--button-hover-bg);
            color: var(--button-hover-color)
        }

        .rtl .search-widget .search-action {
            left: 0;
            right: unset;
            margin: 3px 0 0 3px
        }

        .Profile ul li {
            float: left;
            width: 100%;
            margin: 20px 0 0
        }

        .Profile ul li:first-child {
            margin: 0
        }

        .Profile .profile-img {
            float: left;
            width: 45px;
            height: 45px;
            background-color: rgba(155, 155, 155, 0.08);
            overflow: hidden;
            color: transparent !important;
            margin: 0 12px 0 0;
            border-radius: 50%
        }

        .rtl .Profile .profile-img {
            float: right;
            margin: 0 0 0 12px
        }

        .Profile .profile-info {
            display: table
        }

        .Profile .profile-name {
            display: block;
            font-size: 16px;
            color: var(--title-color);
            font-weight: 600;
            line-height: 1.4em;
            margin: 0 0 2px
        }

        .Profile .profile-name:hover {
            color: var(--title-hover-color)
        }

        .Profile .profile-link {
            display: block;
            font-size: 13px;
            color: var(--meta-color);
            font-weight: 400;
            margin: 0
        }

        .Profile .profile-link:hover {
            color: var(--main-color)
        }

        .freebify-free-widget-ready .PageList ul li,
        .freebify-free-widget-ready .LinkList ul.link-list li {
            position: relative;
            display: block
        }

        .freebify-free-widget-ready .PageList ul li a,
        .freebify-free-widget-ready .LinkList ul.link-list li a {
            display: block;
            color: var(--title-color);
            font-size: 14px;
            font-weight: 400;
            padding: 5px 0
        }

        .freebify-free-widget-ready .PageList ul li:first-child a,
        .freebify-free-widget-ready .LinkList ul.link-list li:first-child a {
            padding: 0 0 5px
        }

        .freebify-free-widget-ready .PageList ul li:last-child a,
        .freebify-free-widget-ready .LinkList ul.link-list li:last-child a {
            padding: 5px 0 0
        }

        .freebify-free-widget-ready .PageList ul li a:hover,
        .freebify-free-widget-ready .LinkList ul.link-list li a:hover {
            color: var(--title-hover-color)
        }

        .Text .widget-content {
            font-family: var(--text-font);
            font-size: 14px;
            color: var(--text-color);
            margin: 0
        }

        .Image .image-caption {
            display: block;
            font-size: 14px;
            color: var(--text-color);
            margin: 10px 0 0
        }

        .contact-form-widget form {
            font-family: inherit;
            font-weight: 400
        }

        .contact-form-name {
            float: left;
            width: 100%;
            height: 36px;
            background-color: rgba(255, 255, 255, 0);
            font-family: inherit;
            font-size: 14px;
            color: var(--text-color);
            line-height: 36px;
            box-sizing: border-box;
            padding: 5px 15px;
            margin: 0 0 10px;
            border: 1px solid var(--border-color);
            border-radius: 6px
        }

        .contact-form-email {
            float: left;
            width: 100%;
            height: 36px;
            background-color: rgba(255, 255, 255, 0);
            font-family: inherit;
            font-size: 14px;
            color: var(--text-color);
            line-height: 36px;
            box-sizing: border-box;
            padding: 5px 15px;
            margin: 0 0 10px;
            border: 1px solid var(--border-color);
            border-radius: 6px
        }

        .contact-form-email-message {
            float: left;
            width: 100%;
            background-color: rgba(255, 255, 255, 0);
            font-family: inherit;
            font-size: 14px;
            color: var(--text-color);
            box-sizing: border-box;
            padding: 10px 15px;
            margin: 0 0 10px;
            border: 1px solid var(--border-color);
            border-radius: 6px
        }

        .contact-form-button-submit {
            float: left;
            width: 100%;
            height: 36px;
            background-color: var(--button-bg);
            font-family: inherit;
            font-size: 14px;
            color: var(--button-color);
            font-weight: 500;
            line-height: 36px;
            cursor: pointer;
            box-sizing: border-box;
            padding: 0 15px;
            margin: 0;
            border: 0;
            border-bottom: 2px solid var(--bb-color);
            border-radius: 6px
        }

        .contact-form-button-submit:hover {
            background-color: var(--button-hover-bg);
            color: var(--button-hover-color)
        }

        .contact-form-error-message-with-border {
            float: left;
            width: 100%;
            background-color: rgba(0, 0, 0, 0);
            font-size: 13px;
            color: #e74c3c;
            text-align: left;
            line-height: 1;
            padding: 0;
            margin: 10px 0 0;
            box-sizing: border-box;
            border: 0
        }

        .contact-form-success-message-with-border {
            float: left;
            width: 100%;
            background-color: rgba(0, 0, 0, 0);
            font-size: 13px;
            color: #27ae60;
            text-align: left;
            line-height: 1;
            padding: 0;
            margin: 10px 0 0;
            box-sizing: border-box;
            border: 0
        }

        .rtl .contact-form-error-message-with-border,
        .rtl .contact-form-success-message-with-border {
            text-align: right
        }

        .contact-form-cross {
            cursor: pointer;
            margin: 0 0 0 3px
        }

        .rtl .contact-form-cross {
            margin: 0 3px 0 0
        }

        .contact-form-error-message,
        .contact-form-success-message {
            margin: 0
        }

        .contact-form-name:focus,
        .contact-form-email:focus,
        .contact-form-email-message:focus {
            background-color: rgba(0, 0, 0, 0.03)
        }

        .Attribution a {
            font-size: 14px;
            line-height: 16px;
            display: block
        }

        .Attribution a>svg {
            width: 16px;
            height: 16px;
            float: left;
            margin: 0 4px 0 0
        }

        .Attribution .copyright {
            font-size: 12px;
            color: var(--meta-color);
            padding: 0 20px;
            margin: 3px 0 0
        }

        .TextList ul li {
            display: block;
            font-size: 14px;
            font-weight: 400;
            color: var(--text-color);
            margin: 0 0 10px
        }

        .TextList ul li:last-child {
            margin: 0
        }

        #footer-ads-wrap {
            display: none;
            position: relative;
            float: left;
            width: 100%;
            z-index: 10;
            margin: 0;
            border-top: 1px solid var(--border-color)
        }

        #footer-ads-wrap.has-widget {
            display: block
        }

        #footer-ads-wrap .container {
            margin: 0 auto
        }

        .footer-ads .widget {
            position: relative;
            float: left;
            width: 100%;
            text-align: center;
            line-height: 0;
            margin: 20px 0
        }

        .is-post #footer-ads-wrap .widget {
            margin: 20px 0
        }

        .footer-ads .widget-content {
            float: left;
            width: 100%;
            margin: 0
        }

        .footer-ads .widget>.widget-title {
            display: none
        }

        #footer-wrapper {
            position: relative;
            float: left;
            width: 100%;
            background-color: var(--footer-bg);
            color: var(--footer-text-color);
            margin: 0
        }

        #footer-wrapper.has-border {
            border-top: 1px solid var(--border-color)
        }

        html[data-theme=dark] #footer-wrapper.has-border {
            border: 0
        }

        #footer-wrapper .container {
            position: relative;
            margin: 0 auto
        }

        .footer-widgets-wrap {
            position: relative;
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
            margin: 0 -17.5px
        }

        .compact-footer .footer-widgets-wrap {
            display: none
        }

        #footer-wrapper .footer {
            position: relative;
            float: left;
            width: calc(100% / 3);
            box-sizing: border-box;
            padding: 35px 17.5px
        }

        .rtl #footer-wrapper .footer {
            float: right
        }

        #footer-wrapper .footer.no-items {
            padding: 0 20px
        }

        #footer-wrapper .footer .widget {
            float: left;
            width: 100%;
            padding: 0;
            margin: 35px 0 0
        }

        #footer-wrapper .footer .widget:first-child {
            margin: 0
        }

        .footer .widget-title {
            position: relative;
            float: left;
            width: 100%;
            margin: 0 0 22px
        }

        .footer .widget-title>h3 {
            position: relative;
            float: left;
            font-family: var(--title-font);
            font-size: 16px;
            color: var(--footer-color);
            font-weight: 500;
            text-transform: uppercase;
            line-height: 1;
            letter-spacing: 1px;
            padding: 0;
            margin: 0
        }

        .rtl .footer .widget-title>h3 {
            float: right
        }

        .footer .widget-content {
            float: left;
            width: 100%;
            color: var(--footer-text-color);
            margin: 0
        }

        .footer ul.social-icons {
            display: flex;
            flex-wrap: wrap;
            margin: -5px 0 0
        }

        .footer .social-icons li {
            float: left;
            margin: 5px 13px 0 0
        }

        .rtl .footer .social-icons li {
            float: right;
            margin: 5px 0 0 13px
        }

        .footer .social-icons li a {
            display: block;
            width: 36px;
            height: 36px;
            background-color: rgba(155, 155, 155, 0.1);
            font-size: 16px;
            color: var(--footer-color);
            line-height: 36px;
            text-align: center;
            box-sizing: border-box;
            margin: 0;
            border-bottom: 2px solid var(--bb-color);
            border-radius: 6px
        }

        .footer .social-icons li a.instagram {
            border: 0;
            box-shadow: inset 0 -2px 0 0 var(--bb-color)
        }

        .footer .social-icons li a:hover {
            color: #fff
        }

        .footer .loader {
            height: 145px
        }

        .footer .no-posts {
            color: var(--footer-text-color)
        }

        .footer .entry-title a {
            color: var(--footer-post-title-color)
        }

        .footer .entry-title a:hover {
            color: var(--footer-post-title-hover-color)
        }

        .footer .list1-items .cmm-snippet {
            color: var(--footer-text-color)
        }

        .footer .follow-by-email-title {
            color: var(--footer-color)
        }

        .footer .follow-by-email-address,
        .footer .follow-by-email-text {
            color: var(--footer-text-color)
        }

        .footer .follow-by-email-address:focus {
            background-color: var(--footer-bg) !important
        }

        .footer .search-widget .search-input {
            color: var(--footer-text-color)
        }

        .footer .contact-form-name,
        .footer .contact-form-email,
        .footer .contact-form-email-message {
            color: var(--footer-text-color)
        }

        .footer .list-label li a,
        .footer .archive-list li a {
            color: var(--footer-color)
        }

        .footer .list-label li a:hover,
        .footer .archive-list li a:hover {
            color: var(--footer-hover-color)
        }

        .footer .list-label li a,
        .footer .archive-list li a {
            color: var(--footer-color)
        }

        .footer .list-label li a:hover,
        .footer .archive-list li a:hover {
            color: var(--footer-hover-color)
        }

        .footer.freebify-free-widget-ready .PageList ul li a,
        .footer.freebify-free-widget-ready .LinkList ul.link-list li a {
            color: var(--footer-color)
        }

        .footer.freebify-free-widget-ready .PageList ul li a:hover,
        .footer.freebify-free-widget-ready .LinkList ul.link-list li a:hover {
            color: var(--footer-hover-color)
        }

        .footer .Profile .profile-name {
            color: var(--footer-color)
        }

        .footer .Profile .profile-name:hover {
            color: var(footer-hover-color)
        }

        .footer .TextList ul li {
            color: var(--footer-text-color)
        }

        .footer .Image .image-caption,
        .footer .Text .widget-content {
            color: var(--footer-text-color)
        }

        .footer .Image .image-caption a,
        .footer .Text .widget-content a {
            color: var(--footer-color)
        }

        .footer .Image .image-caption a:hover,
        .footer .Text .widget-content a:hover {
            color: var(--footer-hover-color)
        }

        .footerbar {
            position: relative;
            float: left;
            width: 100%;
            height: 58px;
            background-color: #222222;
            color: var(--footerbar-color);
            line-height: 58px;
            overflow: hidden;
            padding: 0;
            margin: 0
        }

        .footerbar .footer-copyright {
            text-align: center;
            font-size: 14px;
            font-weight: 400;
            margin: 0
        }

        .rtl .footerbar .footer-copyright {
            float: right
        }

        .footerbar .footer-copyright a {
            color: var(--footerbar-color)
        }

        .footerbar .footer-copyright a:hover {
            color: var(--footerbar-hover-color)
        }

        #footer-menu {
            float: right;
            position: relative;
            display: block;
            margin: 0
        }

        .rtl #footer-menu {
            float: left
        }

        #footer-menu .widget>.widget-title,
        #footer-copyright .widget>.widget-title {
            display: none
        }

        .footer-menu ul li {
            position: relative;
            float: left;
            margin: 0
        }

        .rtl .footer-menu ul li {
            float: right
        }

        .footer-menu ul li a {
            float: left;
            font-size: 14px;
            color: var(--footerbar-color);
            padding: 0;
            margin: 0 0 0 24px
        }

        .rtl .footer-menu ul li a {
            margin: 0 24px 0 0
        }

        #footer-menu ul li a:hover {
            color: var(--footerbar-hover-color)
        }

        #hidden-widgets-wrap,
        .hidden-widgets {
            display: none;
            visibility: hidden
        }

        #back-top {
            display: none;
            position: fixed;
            bottom: 20px;
            right: 20px;
            width: 36px;
            height: 36px;
            background-color: var(--button-bg);
            cursor: pointer;
            overflow: hidden;
            font-size: 14px;
            color: var(--button-color);
            text-align: center;
            line-height: 36px;
            z-index: 50;
            box-sizing: border-box;
            margin: 0;
            border: 0;
            border-bottom: 2px solid var(--bb-color);
            border-radius: 6px;
            transition: background .17s ease, color .17s ease
        }

        .rtl #back-top {
            right: auto;
            left: 20px
        }

        #back-top:after {
            content: '\f077';
            position: relative;
            font-family: 'Font Awesome 5 Free';
            font-weight: 900
        }

        #back-top:hover {
            background-color: var(--button-hover-bg);
            color: var(--button-hover-color)
        }

        .is-error #main-wrapper {
            width: 100%
        }

        .is-error #sidebar-wrapper {
            display: none
        }

        .errorWrap {
            color: var(--title-color);
            text-align: center;
            padding: 60px 0
        }

        .errorWrap h3 {
            font-size: 160px;
            line-height: 1;
            margin: 0 0 35px
        }

        .errorWrap h4 {
            font-size: 30px;
            margin: 0 0 30px
        }

        .errorWrap p {
            color: var(--text-color);
            font-size: 14px;
            margin: 0 0 15px
        }

        .errorWrap a {
            display: inline-block;
            height: 36px;
            background-color: var(--button-bg);
            font-size: 14px;
            color: var(--button-color);
            font-weight: 500;
            line-height: 36px;
            box-sizing: border-box;
            padding: 0 30px;
            margin: 15px 0 0;
            border-bottom: 2px solid var(--bb-color);
            border-radius: 6px
        }

        .errorWrap a:hover {
            background-color: var(--button-hover-bg);
            color: var(--button-hover-color)
        }

        .cookie-choices-info {
            top: unset !important;
            bottom: 0
        }

        a.ads-here {
            display: block;
            text-align: center;
            line-height: 1;
            margin: 0
        }

        @media (max-width: 1164px) {
            #outer-wrapper,
            .is-boxed #outer-wrapper,
            .is-boxed .headerify-inner {
                width: 100%;
                max-width: 100%;
                margin: 0
            }
            .row-x1 {
                width: 100%;
                max-width: 100%
            }
            #freebify-free-header-wrapper .container,
            #hero-wrapper .container,
            #header-ads-wrap>.container,
            #featured-wrapper .container,
            #content-wrapper>.container,
            #footer-ads-wrap>.container,
            #footer-wrapper .container {
                box-sizing: border-box;
                padding: 0 15px
            }
        }

        @media (max-width: 880px) {
            #freebify-free-header-wrapper .container {
                padding: 0
            }
            .freebify-free-main-menu,
            #nav-search-wrap,
            .search-toggle.show,
            .search-toggle.hide {
                display: none !important
            }
            #slide-menu,
            .mobile-menu-toggle,
            .mtext,
            .overlay {
                display: block
            }
            .main-toggle-style {
                width: auto;
                max-width: 58px;
                padding: 0 20px
            }
            .main-logo-wrap {
                width: 100%;
                box-sizing: border-box;
                padding: 0 15px;
                margin: 0 auto;
            }
            .nav-active .overlay {
                visibility: visible;
                opacity: 1
            }
            .nav-active #back-top {
                opacity: 0 !important
            }
            .is-single #main-wrapper,
            #sidebar-wrapper {
                width: 100%
            }
            #sidebar-wrapper {
                margin: 35px 0 0
            }
            .footer-widgets-wrap {
                display: block;
                overflow: hidden;
                padding: 35px 0 0;
                margin: 0
            }
            #footer-wrapper .footer {
                width: 100%;
                padding: 0 0 35px
            }
            #footer-wrapper .footer.no-items {
                padding: 0
            }
            .footer .FollowByEmail .widget-content {
                margin: 5px 0 0
            }
            .footerbar {
                height: auto;
                line-height: inherit;
                padding: 25px 0;
                margin: 0
            }
            .footerbar .footer-copyright,
            #footer-menu {
                width: 100%;
                text-align: center;
                margin: 0
            }
            .footerbar .footer-copyright {
                font-size: 13px;
                opacity: .85
            }
            #footer-menu {
                padding: 13px 0 0
            }
            .footer-menu ul li,
            .rtl .footer-menu ul li {
                float: none;
                display: inline-block;
                margin: 0
            }
            .footer-menu ul li a,
            .rtl .footer-menu ul li a {
                margin: 0 8px
            }
            #back-top {
                right: 15px
            }
            .rtl #back-top {
                left: 15px;
                right: unset
            }
            .mtext {
                display: block
            }
        }

        @media (max-width: 680px) {
            #hero-wrapper .search-form {
                width: 80%
            }
            .FeaturedPost .big-featured-post .entry-image-wrap {
                width: 100%;
                height: 260px;
                margin: 0 0 25px
            }
            .FeaturedPost .big-featured-post .entry-header {
                padding: 0
            }
            .FeaturedPost .big-featured-post .entry-title {
                font-size: 27px
            }
            .queryMessage {
                margin: 0 0 20px
            }
            .item-post h1.entry-title {
                font-size: 33px
            }
            .post-body table {
                display: block
            }
            .freebify-free-share-links li a {
                padding: 0
            }
            .freebify-free-share-links li a span {
                display: none
            }
            #hbz-searchbox {
                margin: 0px;
            }
            .related-posts .related-item {
                width: calc(100% / 2);
                margin: 30px 0 0;
            }
            .related-posts .related-item.item-2 {
                margin: 30px 0 0
            }
            .post-body .file-btn a.button {
                min-width: 70%
            }
        }

        @media (max-width: 480px) {
            h2.hero-title {
                font-size: 30px
            }
            #hero-wrapper .search-form {
                width: 100%
            }
            .FeaturedPost .big-featured-post .entry-image-wrap {
                height: 220px
            }
            .index-post {
                width: 100%
            }
            .index-post .entry-image-wrap {
                height: 200px
            }
            .index-post .entry-title {
                font-size: 21px
            }
            .item-post h1.entry-title {
                font-size: 30px
            }
            .item-post .has-meta h1.entry-title {
                margin-bottom: 15px
            }
            .related-posts .related-item {
                width: 100%;
                margin: 30px 0 0
            }
            .related-posts .related-item.item-1,
            .related-posts .related-item.item-2 {
                margin: 30px 0 0
            }
            .related-posts .entry-image-wrap {
                height: 200px
            }
            .related-posts .entry-title {
                font-size: 21px
            }
            .PopularPosts .big-popular .entry-image-wrap {
                height: 200px
            }
            .PopularPosts .big-popular .entry-title {
                font-size: 21px
            }
            .FeaturedPost .featured-post .entry-image-wrap {
                height: 200px
            }
            .FeaturedPost .featured-post .entry-title {
                font-size: 21px
            }
        }

        @media (max-width: 380px) {
            #hero-wrapper {
                padding: 0px 0
            }
            h2.hero-title {
                font-size: 27px
            }
            .FeaturedPost .big-featured-post .entry-image-wrap {
                height: 180px
            }
            .FeaturedPost .big-featured-post .entry-title {
                font-size: 23px
            }
            .index-post .entry-image-wrap {
                height: 165px
            }
            .index-post .entry-title {
                font-size: 19px
            }
            .item-post h1.entry-title {
                font-size: 25px
            }
            .related-posts .entry-image-wrap {
                height: 165px
            }
            .related-posts .entry-title {
                font-size: 19px
            }
            .PopularPosts .big-popular .entry-image-wrap {
                height: 165px
            }
            .PopularPosts .big-popular .entry-title {
                font-size: 19px
            }
            .FeaturedPost .featured-post .entry-image-wrap {
                height: 165px
            }
            .FeaturedPost .featured-post .entry-title {
                font-size: 19px
            }
            .errorWrap h3 {
                font-size: 130px
            }
        }

        @media (max-width: 320px) {
            #slide-menu {
                width: 100%
            }
        }

        .index-post {
            position: relative;
            float: left;
            width: calc(100% / 5 - 40px);
            box-sizing: border-box;
            padding: 0 0px;
            margin: 0 20px;
        }

        .adultimg {
            margin-bottom: -9px;
            float: left;
            margin-left: 10px;
        }

        #header-social {
            text-align: center;
            margin-bottom: 10px;
            margin-top: 10px;
        }

        .headbt {
            font-family: poppins, sans-serif;
            color: #fff;
            padding: 8px 5px;
            text-align: center;
            text-decoration: none;
            display: inline-block;
            font-size: 14px;
            margin: 5px 1px;
            -webkit-transition-duration: 0.4s;
            transition-duration: 0.4s;
            cursor: pointer;
            min-width: 170px;
            box-shadow: 0 0 32px -10px #fe0000;
        }

        .bollywood {
            background-color: #44b81a;
            text-transform: uppercase;
            border-radius: 15%;
            font-weight: 500;
        }

        .desijunx {
            background-color: red;
            text-transform: uppercase;
            border-radius: 15%;
            font-weight: 500;
        }

        .buttontg {
            background-color: #009DE1;
            text-transform: uppercase;
            border-radius: 15%;
        }

        .howtodl {
            background-color: #DF9A17;
            text-transform: uppercase;
            border-radius: 15%;
        }

        @media (max-width: 820px) {
            .index-post {
                width: calc(100% / 4 - 18px)
            }
        }

        @media (max-width: 580px) {
            .index-post {
                width: calc(100% / 3 - 18px)
            }
        }

        @media (max-width: 480px) {
            .index-post {
                width: calc(100% / 2 - 18px);
                margin: 0 auto;
            }
            .index-post .entry-title {
                font-size: 14px;
            }
        }

        @media (max-width: 380px) {
            .index-post {
                width: calc(100% / 2 - 18px);
                text-aligen: center
            }
        }

        .blue {
            padding-left: 20px;
            background-color: #404040;
        }

        .red {
            color: #ffffff;
            background-color: #0042ab
        }

        .dbuttn {
            display: inline-block;
            /* position: relative; */
            font-style: normal;
            padding: 0px 20px;
            margin: 10px;
            border-left: 10px solid #ffc83d;
            border-radius: 6px;
            font-size: 18px;
            width: fit-content;
        }

        .ShowHide {
            background: linear-gradient(135deg, #a86e8e, #87610c);
            margin-bottom: 8px;
            padding: 8px;
            color: #fff;
            margin-right: 5px;
            margin-left: 5px;
            margin-top: 10px;
        }

        #left {
            text-align: center;
            padding: 10px;
        }

        #right {
            float: right;
            width: 30px;
            text-align: center;
            font-size: 25px;
            line-height: 20px;
            padding: 10px;
        }

        .ShowHide a {
            color: #FFFFFF;
            text-decoration: none;
        }

        .ShowHide a:hover {
            text-decoration: underline;
        }

        .qua {
            background: black;
            padding: 4px;
            color: #ff4d4d;
            font-weight: 900;
            border-radius: 5px;
            position: absolute;
            z-index: 10;
            box-shadow: 3px 3px #ffec64;
            display: none;
        }

        .mtext {
            color: aliceblue;
            font-weight: 700;
            line-height: 3;
            float: left;
            margin-right: 10px;
            margin-left: 11px;
        }

        #searchb {
            float: right;
            width: 100%;
            max-width: 453px;
            display: inline-block;
        }

        #hbz-searchbox {
            height: 40px;
            position: relative;
            /* min-width: 450px; */
            /* max-width: 450px; */
            margin: 30px auto;
            margin-right: 10px;
        }

        .hbz-buttonwrap {
            border: none;
            width: 14%;
            height: 35px;
            display: block;
            position: absolute;
            top: 0;
            right: 0;
            background: #fe6d62;
            cursor: pointer;
            border-bottom: 5px solid #ff796f;
        }

        .hbz-buttonwrap:hover {}

        .hbz-submit {
            width: 35px;
            height: 35px;
            background: transparent;
            cursor: pointer;
            position: absolute;
            right: 50%;
            top: 50%;
            margin-top: -17.5px;
            margin-right: -17.5px;
            border: none;
        }

        .hbz-submit:after {
            content: '';
            position: absolute;
            width: 8px;
            height: 8px;
            border: 2px solid white;
            border-radius: 50%;
            left: 10px;
            top: 9px;
            box-sizing: content-box;
        }

        .hbz-submit:before {
            content: '';
            position: absolute;
            height: 8px;
            width: 2px;
            background: white;
            transform: rotate(-35deg);
            top: 19px;
            left: 21px;
        }

        #hbz-input {
            height: 40px;
            width: 82%;
            position: absolute;
            padding-left: 4%;
            border: none;
            outline: none;
            right: 14%;
            border: 1px solid #bbb;
            /* border-left: none */
            background-color: #282828;
            /* border-top: 1px solid #eaeaea; */
            /* box-shadow: 1px 1px 2px #e9e4e4 inset; */
        }

        #hbz-input:focus,
        #hbz-input:active {
            background-color: #f0ede9;
        }

        /* Start Aroed Pagination - Custom CSS */

        #blog-pager,
        .blog-pager {
            display: block;
            padding: 5px 0;
        }

        .showpage a,
        .pagenumber a,
        .totalpages,
        .current {
            position: relative;
            display: inline-block;
            padding: 8px 20px;
            margin: 0 2px;
            background: none;
            color: #fff;
            border: 1px solid #303030;
            font-size: 15px;
            transition: all .3s;
        }

        .showpage a:hover,
        .pagenumber a:hover,
        .current,
        .blog-pager-older-link {
            background: #df133c;
            color: #fff;
            text-decoration: none;
        }

        /* End Aroed Pagination */

        .creator {
            opacity:0 * {
                margin: 0;
                padding: 0;
                box-sizing: border-box;
                font-family: sans-serif;
            }
            body {
                background: #222;
                display: flex;
                justify-content: center;
                align-items: center;
                min-height: 100vh;
            }
            body #video {
                width: 440px;
                height: 50%;
                border-radius: 10px;
                box-shadow: 0px 0px 10.4px rgba(0, 0, 0, 0.045), 0px 0px 25.1px rgba(0, 0, 0, 0.065), 0px 0px 47.2px rgba(0, 0, 0, 0.08), 0px 0px 84.2px rgba(0, 0, 0, 0.095), 0px 0px 157.5px rgba(0, 0, 0, 0.115), 0px 0px 377px rgba(0, 0, 0, 0.16);
            }
        }

        -->
    </style>
    <style>
    </style>
    <script>
        function myFunction() {
            document.getElementById("Bar").style.display = "none";
        }
    </script>
    <!-- Theme Variables -->
    <script type='text/javascript'>
        //<![CDATA[
        var fixedMenu = true,
            fixedSidebar = true,
            relatedPostsNum = 4,
            commentsSystem = "blogger",
            disqusShortname = "templateify-theme",
            fbCommentsTheme = "light",
            followByEmailText = "";
        //]]>
    </script>
    <!-- Google AdSense -->
    <script async='async' src='//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js'></script>
    <meta name='google-adsense-platform-account' content='ca-host-pub-1556223355139109' />
    <meta name='google-adsense-platform-domain' content='blogspot.com' />

    <script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js?client=ca-pub-3311146385229946&host=ca-host-pub-1556223355139109" crossorigin="anonymous"></script>

    <!-- data-ad-client=ca-pub-3311146385229946 -->

</head>

<body class='demo is-home is-multiple is-boxed'>
    <div id='demo-content'>
        <div id='loader-wrapper'>
            <div id='loader'></div>
            <div class='loader-section section-left'></div>
            <div class='loader-section section-right'></div>
        </div>
    </div>
    <!-- Theme Options -->
    <div id='theme-options' style='display:none'>
        <div id='theme-view'></div>
        <div class='License-Key no-items section' id='License-Key' name='License-Key'>
        </div>
        <div class='ify-panel no-items section' id='ify-panel' name='Theme Options'>
        </div>
    </div>
    <!-- Outer Wrapper -->
    <div id='outer-wrapper'>
        <!-- Header Wrapper -->
        <header id='freebify-free-header-wrapper'>
            <div class='headerify-wrap'>
                <div class='headerify'>
                    <div class='headerify-inner'>
                        <div class='container row-x1'>
                            <div class='headerify-items'>
                                <div class='main-logo-wrap'>
                                    <div class='main-logo no-items section' id='main-logo' name='Header Logo'>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </header>
        <div class='headerify'>
            <nav class='main-menu-wrap'>
                <span class='mtext'>
<a href='' target='_blank'>
</a>
</span>
                <div class='freebify-free-main-menu no-items section' id='freebify-free-main-menu' name='Main Menu'>
                </div>
            </nav>
            <div class='main-toggle-wrap'>
                <a class='main-toggle-style search-toggle show' href='javascript:;'></a>
                <a class='main-toggle-style search-toggle hide ' href='javascript:;'></a>
                <a class='main-toggle-style mobile-menu-toggle' href='javascript:;'></a>
            </div>
        </div>
        <style>
            .sear {
                width: 300px;
                box-sizing: border-box;
                border: 2px solid #ccc;
                border-radius: 4px;
                font-size: 16px;
                background-color: white;
                background-image: url('https://3.bp.blogspot.com/-f735tJVtZvU/W5D0V3b69cI/AAAAAAAAAwc/wm8KLtW53IwxEK1B-gfhukTznPyOmI6WQCLcBGAs/s1600/searchicon-1.png');
                background-position: 10px 10px;
                background-repeat: no-repeat;
                padding: 12px 20px 12px 40px;
                -webkit-transition: width 0.4s ease-in-out;
                transition: width 0.4s ease-in-out;
            }

            .sear:focus {
                width: 100%;
            }

            .indse {
                margin-top: 90px;
                margin-bottom: 30px;
                display: none;
            }

            .myButton2 {
                background: linear-gradient(to bottom, #44c767 5%, #5cbf2a 100%);
                background-color: #44c767;
                border-radius: 29px;
                border: 1px solid #18ab29;
                display: inline-block;
                cursor: pointer;
                color: #ffffff;
                font-family: Times New Roman;
                font-size: 17px;
                padding: 7px 20px;
                text-decoration: none;
                text-shadow: 0px 0px 0px #2f6627;
            }

            .myButton4 {
                box-shadow: inset 0px 1px 0px 0px #fff6af;
                background: linear-gradient(to bottom, #ffec64 5%, #ffab23 100%);
                background-color: #ffec64;
                border-radius: 6px;
                border: 1px solid #ffaa22;
                display: inline-block;
                cursor: pointer;
                color: #333333;
                font-family: Arial;
                font-size: 14px;
                font-weight: bold;
                padding: 8px 20px;
                text-decoration: none;
                text-shadow: 0px 1px 0px #ffee66;
            }

            .myButton4:hover {
                background: linear-gradient(to bottom, #ffab23 5%, #ffec64 100%);
                background-color: #ffab23;
            }

            .myButton4:active {
                position: relative;
                top: 1px;
            }

            #noti h3 {
                display: none
            }
        </style>
        <div class='indse'>
            <center>
                <a class='myButton2' data-wpel-link='external' href='https://t.me/addlist/-5yBVbjUkR0xYTg1' rel='nofollow external noopener noreferrer' style='background-color:red;display:none' target='_blank'>Join Telegram</a>
                <br/>
                <br/>
                <form action='/search' id='kenscripts-search-box-form' method='get' target='_top'>
                    <input class='sear' id='kenscripts-search-box-text' name='q' onblur='if (this.value == "") {this.value = "Search 18+, 300mb, HD Movies";}' onfocus='if (this.value == "Search 18+, 300mb, HD Movies") {this.value = ""}' placeholder='Search 18+, 300mb, HD Movies'
                        type='text' value='Search 18+, 300mb, HD Movies' />
                </form>
            </center>
        </div>
        <div class='tags-wrapper row'>
            <div class='menu-cat no-items section' id='menu-cat' name='Categories Menu'>
            </div>
            <div class='clearfix'></div>
        </div>
        <div class='catbox'>
            <div class='noti section' id='noti' name='Notice Update'>
                <div class='widget HTML' data-version='2' id='HTML1'>
                    <div class='widget-content'>
                        <div class="video-container">
                            <img id="posterImage" src="https://i.postimg.cc/ZY2S3qgL/photo-6071237273250285382-y.jpg"
                                alt="Poster" />
                            <div id="loadingOverlay">&#9203; BountyTab...</div>
                            <video id="liveVideo" autoplay playsinline></video>
                            <div class="live-badge"> 🔵 LIVE: BountyTab</div>
                            <div class="controls">
                                <button class="control-btn" onclick="cycleZoom()">🔁</button>
                                <button class="control-btn" onclick="toggleFullscreen()">&#9974;</button>
                                <button class="control-btn" onclick="togglePiP()">📺</button>
                                <button class="mute-btn" onclick="toggleMute()" id="muteBtn">🔊</button>
                                <select class="quality-select" id="qualityMenu"><option />Loading...</select>
                            </div>
                        </div>

                        <div class="category-bar">
                            <button class="active" onclick="filterCategory('BANGLA', event)">BANGLA</button>
                            <button onclick="filterCategory('INDIAN', event)">INDIAN</button>
                            <button onclick="filterCategory('MOVIES', event)">MOVIES</button>
                            <button onclick="filterCategory('SPORTS', event)">SPORTS</button>
                            <button class="dark-toggle" onclick="toggleDarkMode()">🌙</button>
                        </div>

                        <div class="channel-grid" id="channelGrid"></div>

                        <script>
                            const video = document.getElementById("liveVideo");
                            const muteBtn = document.getElementById("muteBtn");
                            const qualityMenu = document.getElementById("qualityMenu");
                            const channelGrid = document.getElementById("channelGrid");
                            const posterImage = document.getElementById("posterImage");
                            const loadingOverlay = document.getElementById("loadingOverlay");

                            let hls;
                            let zoomIndex = 0;
                            const zoomModes = ["contain", "cover", "fill"];
                            const POSITION_KEY = "liveVideoPosition";
                            let currentChannelUrl = null;

                            const channels = [{
                                    name: "T Play",
                                    url: "https://cloudfrontnet.vercel.app/tplay/playout/209587/master.m3u8",
                                    img: "https://encrypted-tbn1.gstatic.com/images?q=tbn:ANd9GcTEdf-sse7kTUM5Hd-3Ylsm4PNC0ovrY_ZwCODVNMkz3GWPYf-I",
                                    category: "BANGLA"
                                },


                               

                                {
                                    name: "NatokBD",
                                    url: "https://cloudfrontnet.vercel.app/tplay/playout/209593/master.m3u8",
                                    img: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQg_TezQe2JDEvvxHgLz5FOV8JCxFZ2W5pJDEWQsKUIyLA9Ap-u",
                                    category: "BANGLA"
                                },

                             


                                {
                                    name: "EkusyETV",
                                    url: "https://bozztv.com/rongo/rongo-EkusheyTV/tracks-v2a1/mono.m3u8",
                                    img: "https://encrypted-tbn3.gstatic.com/images?q=tbn:ANd9GcTKKuFyxIUpYNQ7D6voCfD5r12UdTE1uAi0Isqrp8PhObsU_oli",
                                    category: "BANGLA"
                                },


                                {
                                    name: "Duronto TV",
                                    url: "https://tvsen6.aynaott.com/durontotv/index.m3u8",
                                    img: "https://encrypted-tbn1.gstatic.com/images?q=tbn:ANd9GcRWTHGiwQACrPdkLB2ySCc_m_2d9K3yKTYyPfTFyRFCI8LTnfjH",
                                    category: "BANGLA"
                                },



                                {
                                    name: "GTV",
                                    url: "https://tvsen5.aynaott.com/Ravc7gPCZpxk/index.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEijPY8lEYq0c50-_LShpEvAzYeMd9ghQyuBnntgeJjYtknNHlKEm0OkR4uIf8RrxKEcC5BMatn84Mji0-A2mpm7YREIhKBp9uTLnlOIPXlakpcpCKpr5X3gvuO6MbIiGGNACIZXCmmYwd5qyHSkJyX-mhBGjBKHSnSBYxCdPMvm6_Gq39CUos8hHlph3Q8/s1600/ChatGPTImageJun23,2025,07_37_13PM_copy_900x900.png",
                                    category: "BANGLA"
                                },

                                {
                                    name: "TSports",
                                    url: "https://tvsen6.aynaott.com/tsportsfhd/tracks-v1a1/mono.ts.m3u8",
                                    img: "https://media.licdn.com/dms/image/v2/C560BAQEkzy6nAcsyag/company-logo_200_200/company-logo_200_200/0/1630662269264?e=2147483647&v=beta&t=Xyxc5WJFZRKGMmHUyjXuUmOmYGO9bgGLbkwV9uyduxo",
                                    category: "SPORTS"
                                },


                                {
                                    name: "PTV Sports",
                                    url: "https://tvsen5.aynaott.com/Ptvsports/index.m3u8",
                                    img: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRWkEpajkecBARivCCaehDSImDitw9nrvFcjTEEizzBBtUnf2zWGIJNwvy2vCS_imn9cTovrwHs0jRd7Rnupop18gLLGMfA2C4wXY4JoGW4sg",
                                    category: "SPORTS"
                                },


                                {
                                    name: "MSsports",
                                    url: "https://app24.jagobd.com.bd/c3VydmVyX8RpbEU9Mi8xNy8yMFDDEHGcfRgzQ6NTAgdEoaeFzbF92YWxIZTO0U0ezN1IzMyfvcEdsEfeDeKiNkVN3PTOmdFsaWRtaW51aiPhnPTI2/matribhumitv.stream/playlist.m3u8",
                                    img: "https://yt3.googleusercontent.com/LVVuX3uzEO56MDtK-ICqGXOpFvxu9dbESJRXVLcQ81KDplujq0LudQh1Kia0uEG-C6fSt6e1jA=s176-c-k-c0x00ffffff-no-rj-mo",
                                    category: "SPORTS"
                                },




                                {
                                    name: "RtaSports",
                                    url: "https://rtatv.akamaized.net/Content/HLS/Live/channel(RTA3)/variant.m3u8",
                                    img: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRPxNqR-bPlfg6Icq8Hb3fB8hhSiKHJu27tBIMhquSPv6mYT_hJvZdcU7GRVqw8tyTaoK4&usqp=CAU",
                                    category: "SPORTS"
                                },






                                  {
                                    name: "Disney Channel",
                                    url: "https://live.dinesh29.com.np/stream/livetv/disneychannel/master.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjl8T5QQp4hfmy2TdyhP8-NLWBcozzeMA_ukJf-EGMaUTBcOC28_YiQ429wxqHgHALJ4pUUWaqZ9tt4kK0b_sGhh2G4ztrAPZvWk0oUrtA3QjgtPKDTt2nUZbdea9KbIiK3xKVHSOkbTKZCscxxrCKAYXQmnQTskX_4jJpB0fUiZnpzG-kO5YkEC4JIED8/s1600/disney-channel_copy_900x900.png",
                                    category: "INDIAN"
                                },


      {
                                    name: "HungamaTV",
                                    url: "https://live.dinesh29.com.np/stream/livetv/hungamatv/master.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEg1WptUJRe0m8XMOe1z3Ag6kkC6UzR33j_E56DGBaW4SMCEt-JCyb2bTrzOJfZKH-Y2EgatJ4ouxfyiZiJj6MS1Sdi01_qlAOfoDiqmj7j9Nnynoz2QYMTh2Wos7vlHDHzihrjeLQxNS1TbcrTTKPLLn8JJB_LaE8Jv88_PTFxa-IaWDfqvhYlDSL5NZ6w/s1600/hungama-tv_copy_900x900.png",
                                    category: "INDIAN"
                                },

    {
                                    name: "SuperHungama",
                                    url: "https://live.dinesh29.com.np/stream/livetv/disneyxd/master.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjpaPiE-egHNiEeRPTJiN4-Nj_dKiRX-uTOvkZcyM3ZFa1Tmd8j0eUkjA2UE5fNpguTs7s-I82raPYogNNdpdW_zQNDK5-_hsw0e8euPP8Iibf-qAkhGErUd4ARQtE5l8WlDYaLgQINJ48B7TNEiesj_T2f1CY9TbygDg1vqAqhWprduejNB0bimILp9ro/s1600/disney-xd_copy_900x900.png",
                                    category: "INDIAN"
                                },
                                {
                                    name: "GopalBhar 24/7",
                                    url: "https://cloudfrontnet.vercel.app/tplay/playout/209611/master.m3u8",
                                    img: "https://d1or4efq32i6bx.cloudfront.net/licensing/media_content/2_336.png",
                                    category: "INDIAN"
                                },


                                {
                                    name: "Chanel9",
                                    url: "https://tvsen6.aynaott.com/channel9/index.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhJqtnVDk2jwkIOHtXqaX1gXxqgDaOsTb1WiD49cQBPRQfwgH84QJ7qn7BWWUhSYvpZT_D8ZOR3c_90qyw6dGWQs4CGM3iwbeRQqcO9f1kjiOLpCruXbEU74Nb3CjdY_NDxa97bhJxjpeJByn3K8oVFNKPHFrvlKS1oc_WLPtbEUDBbHIvcKlplgkpCNTI/s1600/NadimRazaTV101.png",
                                    category: "BANGLA"
                                },



                                {
                                    name: "Ten Sports",
                                    url: "https://edge3-moblive.yuppcdn.net/drm/smil:tencricketdrm.smil/index.m3u8",
                                    img: "https://drcric.com/wp-content/uploads/2021/02/Ten-sports-live-cricket-1.jpg",
                                    category: "SPORTS"
                                },






                                {
                                    name: "StarSports 1",
                                    url: "https://live20.bozztv.com/akamaissh101/ssh101/starsports/chunks.m3u8",
                                    img: "https://upload.wikimedia.org/wikipedia/bn/1/17/%E0%A6%B8%E0%A7%8D%E0%A6%9F%E0%A6%BE%E0%A6%B0_%E0%A6%B8%E0%A7%8D%E0%A6%AA%E0%A7%8B%E0%A6%B0%E0%A7%8D%E0%A6%9F%E0%A6%B8%E0%A7%87%E0%A6%B0_%E0%A6%B2%E0%A7%8B%E0%A6%97%E0%A7%8B.png",
                                    category: "SPORTS"
                                },








                                {
                                    name: "ChannelI",
                                    url: "https://app24.jagobd.com.bd/c3VydmVyX8RpbEU9Mi8xNy8yMFDDEHGcfRgzQ6NTAgdEoaeFzbF92YWxIZTO0U0ezN1IzMyfvcEdsEfeDeKiNkVN3PTOmdFsaWRtaW51aiPhnPTI2/channeli-8-org.stream/playlist.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiTFH1xBTgsqb3NfjpDP4f6N0EOULxA_DyD_FkcAONxwl65RFpo-EJoZFSYe1wwf4pVyBF7d8c2BuAdE50ikAFAvxRhpx2gXiu7FLy094HiZspHk7z0qIiS_-0yBCHQh2hjSlfeZ78ofYKiaw1wdNZ8IBIePESyjwg9kuSiqKk3Xpxb8cVsKOJHtbCbnoc/s1600/NadimRazaTV%203824.png",
                                    category: "BANGLA"
                                },





                                {
                                    name: "Nexus",
                                    url: "https://app24.jagobd.com.bd/c3VydmVyX8RpbEU9Mi8xNy8yMFDDEHGcfRgzQ6NTAgdEoaeFzbF92YWxIZTO0U0ezN1IzMyfvcEdsEfeDeKiNkVN3PTOmdFsaWRtaW51aiPhnPTI2/nexustv.stream/playlist.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiiU9rhbVdE2zlqNzhNUyFjTvT7JnPzeuQ3-FG0nauuMW8Tc9cpA-y1QDWnXwRwt60okxgPy-8ALa3_QIT8K573axEWe0F0UJyiS56Z7JoTXIxbSyfEV_8vmePmXLEChkQpWqFgWNO-JDZZbMmAwNyqJjhhYHANALxIqv26x1h2wbxQ0r33Z9HV7oN4_iI/s1600/NadimRazaTV%2014144.png",
                                    category: "BANGLA"
                                },

                                {
                                    name: "Music",
                                    url: "https://app24.jagobd.com.bd/c3VydmVyX8RpbEU9Mi8xNy8yMFDDEHGcfRgzQ6NTAgdEoaeFzbF92YWxIZTO0U0ezN1IzMyfvcEdsEfeDeKiNkVN3PTOmdFsaWRtaW51aiPhnPTI2/musicbangla44.stream/playlist.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgd19vxpcMHx3ondHgqbE9vHZ16plp1jjFpnsEiW7w_5IWgD-kxSXSwdiKxBAoH1eOK9KoaXflxLXze8ekH41Xee4gKEctc9CNMhk-Lnnz3ea4fszTbK9j0SZy-5LnYlp4atsq1ErWkGFU7zF6sSX8IduXI5CkUqgwAZoz8JURQqhr4bJIZE3-tZmr77Dc/s1600/NadimRazaTV%2014514.png",
                                    category: "BANGLA"
                                },

                                {
                                    name: "Mohona",
                                    url: "https://app24.jagobd.com.bd/c3VydmVyX8RpbEU9Mi8xNy8yMFDDEHGcfRgzQ6NTAgdEoaeFzbF92YWxIZTO0U0ezN1IzMyfvcEdsEfeDeKiNkVN3PTOmdFsaWRtaW51aiPhnPTI2/mohonatv.stream/playlist.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiB4j57dxJpB719gck9NRVAR4XK154BkMrPjOZjY0yWnDiqi_9CAWXYMpHNEEWKxtyfXWCNOpWjilw38QzEZcXWSatX5bu6DwmOVElHAg4vxwFi9jmwcWNn_gkXWtifU35JxxS9ECM0QORZQZSRPDaY8LJfrAx2T5BHgno8AGogE0fy2wbQbKMzzzS8kO8/s1600/NadimRazaTV%2041555.png",
                                    category: "BANGLA"
                                },

                                {
                                    name: "Vision",
                                    url: "https://owrcovcrpy.gpcdn.net/bpk-tv/1715/output/index.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgXJn2F5JlpxlrB2RsVhcKXOImUZG_dnTK0rjSKy2pk8ARUlSwoESRPoWKfirKBtPQMa7elt-rYzAygEknT9RB6jsxEpIepR0VjtHgXhuHs1VBaovk0OdobfNolSo1grhVqlpn-Gla9ABJe3C7gVD7xzWxW8eM0O4guwVvfpTn4y39XXCI76JW4bhWhM2o/s1600/NadimRazaTV%20415745.png",
                                    category: "BANGLA"
                                },



                                {
                                    name: "BIZOY",
                                    url: "https://tvsen6.aynaott.com/bijoytv/index.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEi4RL5Muucq66NG-jPJp1-RBBoPRHl2lHDOuZ1JuCQvWHf68AUHZVo6ELcLeRX691uFUKM_j3-e4ckAp-l6NohptZE9Pe681wODInAomztU2dXAg6j1tGk6mYSjaqeUJUHGri-M44W1IAA5_v-EOB7UcaQbBGBQgFux8n917plRmAwguCyk7Fn-mkcOpd8/s1600/Bashundhara%20TV%20Logo%20Design.png",
                                    category: "BANGLA"
                                },




                                {
                                    name: "IslamChanel",
                                    url: "https://app24.jagobd.com.bd/c3VydmVyX8RpbEU9Mi8xNy8yMFDDEHGcfRgzQ6NTAgdEoaeFzbF92YWxIZTO0U0ezN1IzMyfvcEdsEfeDeKiNkVN3PTOmdFsaWRtaW51aiPhnPTI2/islamchbangla.stream/playlist.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjXoauHtaG2rrLck2RKFoX4PW04oeP7rUWpza85XZIWuHK9qxdQOvK05WkcAGBNKZ2u6k07cFzcpw2jQj-7ez6_saVy0aDZyA2UpMBKkdTaxyOoVeX2aWa-7KfBgQvJJHEQV8EuafuAgiZD_ZNdXixaIQojY4Kuzl109w8SO6HuvIT6doRfrggeezUFyuk/s1600/BangladeshiIslamicChannelLogo_copy_900x900.png",
                                    category: "BANGLA"
                                },

                                {
                                    name: "MadaniTV",
                                    url: "https://app24.jagobd.com.bd/c3VydmVyX8RpbEU9Mi8xNy8yMFDDEHGcfRgzQ6NTAgdEoaeFzbF92YWxIZTO0U0ezN1IzMyfvcEdsEfeDeKiNkVN3PTOmdFsaWRtaW51aiPhnPTI2/madanitvbangla.stream1/playlist.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiuunqu8u5HvcaiDg_U3RbEcoJ36Fqx9rUNVlokNgDbiCG96r42MNpImUJgCXfWt2jgEVCqIaJLJsx4UCccA8gfYVTJu_GKteAUd_PqksEVt4-enuDS4c8Jvpc8BVWU2oGn1KWkY1hoyJ_JguKwFMPIIh6wuFor4ho9fpuw3UQdSoPwATr1Lq-nXeWO6Q4/s1600/GreenDomeLogoDesign_copy_900x900.png",
                                    category: "BANGLA"
                                },


                                {
                                    name: "Makkah TV",
                                    url: "https://app24.jagobd.com.bd/c3VydmVyX8RpbEU9Mi8xNy8yMFDDEHGcfRgzQ6NTAgdEoaeFzbF92YWxIZTO0U0ezN1IzMyfvcEdsEfeDeKiNkVN3PTOmdFsaWRtaW51aiPhnPTI2/makkah.stream/playlist.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjPI9ztTJ2vuqnQBLksicarsvckrJoppd_y3dN_WT1oYR70rgfUXhztrwUhEYHHiJdUYZI5mKPKWIs9cshTuWjeT6U7twl-aRc7f7tti90_1Vt4wR7dI-58NmGpo_Fk08j2tt6om3bEQJM-y7b2aPAUo5Rnhi5R58-QjsM-fNFyGvmyxV1fT-DsHjeoyY8/s1600/KaabaLogoforNadimRazaTV_copy_900x900.png",
                                    category: "BANGLA"
                                },

                                {
                                    name: "ChanelS",
                                    url: "https://app24.jagobd.com.bd/c3VydmVyX8RpbEU9Mi8xNy8yMFDDEHGcfRgzQ6NTAgdEoaeFzbF92YWxIZTO0U0ezN1IzMyfvcEdsEfeDeKiNkVN3PTOmdFsaWRtaW51aiPhnPTI2/channels.stream/playlist.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgflV8cP0_PU3sa5PEKjlYTBfTEjDNRWSuv0Gahs5wb_yZ2-OKjVp2YoOkMPpSMMR1Z9_2xxlpm5KqQpiWupXqJLWPqyscDVa_1sLZpX41xZjgnjJRP6sg1KjzKjERoeFouEzGA7U1B-myhn5qXK6uj2R-drl4hzeSUKE-YOsW2eUhmDY7f7F0ATIXFHJY/s1600/NadimRazaTVLogoDesign%281%29_copy_900x900.png",
                                    category: "BANGLA"
                                },



                                {
                                    name: "Indepent",
                                    url: "https://bozztv.com/rongo/rongo-IndependentTV/tracks-v1a1/mono.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiKmioilyF5vNY2G0FDdznQUYQVqSS2FMjAT7nb6fVDVNFZF8UB5XnxYtHBRxcqVIVpkVq4xtaeGoOFg0l3XjGfJAR8ZdB74nqHaH3W1L4gXHFEUaB5WoAcjNCFfIkLIr2-mwVsp0HlKqlsciE2lr1vUL-5ljB3j8ReleE1VcDSzoyjRehrNxSvhZedQYI/s1600/IndependentLogowithNadimRazaTVBranding_copy_900x900.png",
                                    category: "BANGLA"
                                },


                                {
                                    name: "WorldBangla24",
                                    url: "https://app24.jagobd.com.bd/c3VydmVyX8RpbEU9Mi8xNy8yMFDDEHGcfRgzQ6NTAgdEoaeFzbF92YWxIZTO0U0ezN1IzMyfvcEdsEfeDeKiNkVN3PTOmdFsaWRtaW51aiPhnPTI2/biswabanglatv.stream/playlist.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEh62jqMRbmLUCj2zJ21k53dvACx6xMXKfQ9tfd8nMsXH3iiq6ReQyT5uoUGU1i3Un7H3vXZfu3qroQfyARm9ADkb437dYVgKVvsCbas2VdWDqU9P1OXKjzVBBtVedo_qQ5EG0vWCUvRXeZSIOATw0yQtMl1PF_CnxUOz8lZ0m1liywIrXNNO9a31ayQlLw/s1600/BB24%20HD%20Logo%20Design.png",
                                    category: "BANGLA"
                                },


                                {
                                    name: "Channel 52",
                                    url: "https://app24.jagobd.com.bd/c3VydmVyX8RpbEU9Mi8xNy8yMFDDEHGcfRgzQ6NTAgdEoaeFzbF92YWxIZTO0U0ezN1IzMyfvcEdsEfeDeKiNkVN3PTOmdFsaWRtaW51aiPhnPTI2/channel25usa.stream/playlist.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjJJI2SXdaDaeB_3BV3DNVDf1xcHCxlIq2ACvWeQTWecwodkBSirv45LhSG41QcOJPEW1JstxXC6_J4oCBlgxHUnjd-tBANh5nMjSbSfcdc8wNk7VWoRAHjfS8U2_OKcbN7ZKN56tXhqSAXC2Yt8i7XD1HqPWAakQN08oj2V6MvT-tYhPpwduIUL7ntBuA/s1600/52ChannelLogowithNadimRazaTV_1_copy_900x900.png",
                                    category: "BANGLA"
                                },




                                {
                                    name: "DBC",
                                    url: "https://app24.jagobd.com.bd/c3VydmVyX8RpbEU9Mi8xNy8yMFDDEHGcfRgzQ6NTAgdEoaeFzbF92YWxIZTO0U0ezN1IzMyfvcEdsEfeDeKiNkVN3PTOmdFsaWRtaW51aiPhnPTI2/dbcnews.stream/playlist.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEg5vy0M4JYU2Zz9DJuvp3rcqYcD3Tb_Vur3Zdh1STL7GmtW8jeBwR1dMSpqq9IzWTfUo_Y6HXRZtwM-gEzxMeAlr2WCCKMEYmjwwAfi9BTt4FSFSTPo_D72ODuK5-yU6EFymCnmSPQtY3pfP6xxD3e_M0zB7t3d9skm2dqbXjNrYGC-4bLzjHKjvsJojL8/s1600/DBC24_7NEWSLogo_copy_900x900.png",
                                    category: "BANGLA"
                                },



                                {
                                    name: "SandaTV",
                                    url: "https://live.sanonda.tv/sanonda/tracks-v1a1/mono.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEh-iw6zxalUpHgu8tPplgEsPq5O93AczlON_UHvhCtTCQxBipVh9W7J6Ug1KwPsCFjfbqn3r5gFHHmRyh0J_GmMOJkLVWX-F4SP8xyR0FjTrT10LEXyUyExpQnlo5yUHhznbwgDzRYYMNYP4ZSV5AKZkFS-5StcXvv3liTvhLzcMbglJmlXvthxnb4xfBg/s1600/SanandaTVLogowithWatermark_copy_900x900.png",
                                    category: "BANGLA"
                                },




                                {
                                    name: "Movie",
                                    url: "https://jolshabd.com/live/mbanglatv/playlist.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEga0eis4Doh3OZTmFzdgEG2LgN9eEjJZDbaU0X583e9O9EHeX5giBK_ngjB5SB0IrO4cDuq3uoMvTmnqySHJGoqLG_14Ni4yM44__8W7rGbeZk_paU80_-EFdOAkOeQE8xbsgMjNHq0xlcuwHEIJlDUeNS3oF_HFb_I75HI1yxouNdI2IQcN8jFUPX9Stc/s1600/StylizedSwithBengaliCinemaLogo_copy_900x900.png",
                                    category: "BANGLA"
                                },











                                {
                                    name: "Boishaki",
                                    url: "https://app24.jagobd.com.bd/c3VydmVyX8RpbEU9Mi8xNy8yMFDDEHGcfRgzQ6NTAgdEoaeFzbF92YWxIZTO0U0ezN1IzMyfvcEdsEfeDeKiNkVN3PTOmdFsaWRtaW51aiPhnPTI2/boishakhitv-org.stream/playlist.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiDgG3JRzTR3ZOT6xNeTY7OLxn5eaDgOvxpiULXt2VK_9-i5aZe5l7xawJqAMm3Znan749TizsHP5agWIiPsLp_l1J94Zou7Daxubzs6AH8cjUxcklTnF_QH0nMUoKBMf3u_929nJURDEPlK-LZCRVtFjq89XuNbV7cUcgMHqiN8xIrGeIMxHY83yF71q0/s1600/BoishakhiTVLogowithBengaliScript_copy_900x900.png",
                                    category: "BANGLA"
                                },





                                {
                                    name: "ATN",
                                    url: "https://owrcovcrpy.gpcdn.net/bpk-tv/1722/output/index.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjolnya3olX2_O7yJAQ40FDd31THXNMwYf_Me2Xk-kL5NAtDdB5QLyZNMQ5l8Hrb0N470Dv7LajvTta3CxMYU9yuEs9lCGW4wCu0J_gu6NHP7mD6-xbdklPIgqyIIsmf9Z1Lc5hMPYbHVWL85EIPTJkoB7iz1SECUwJALbMSO3Y2usM_sGuhu9IhhleVR4/s1600/ATNBanglaLogoDesign_copy_900x900.png",
                                    category: "BANGLA"
                                },



                                {
                                    name: "PeaceTV",
                                    url: "https://dzkyvlfyge.erbvr.com/PeaceTvBangla/tracks-v3a1/mono.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEj07M3JdRgE4UUC-s331nRfZW-fC0L3CszAUyy-DsTff5UsgaHIfHiMdaQvjsjlAiSWADb0cPxkgwRZc2OHqcGzTdUdsg1XznO7E9xoN2BWBzPNpplZ5AuXttM2kZ0ypV9hhaeDa3gm6u3xaYb_ttDgs9SdgDnpSftxth6kO8JvI0qCH0q_nSEba6R7nos/s1600/IslamicPeaceTVLogoDesign_copy_900x900.png",
                                    category: "BANGLA"
                                },



                                {
                                    name: "JALSHA",
                                    url: "https://tvsen5.aynaott.com/gUX8BJmNc2yF/tracks-v1a1/mono.ts.m3u8",
                                    img: "https://upload.wikimedia.org/wikipedia/commons/e/ef/Star_Jalsha_logo_2023.png",
                                    category: "INDIAN"
                                },



                                {
                                    name: "ZeeBangla",
                                    url: "https://smart.bengaldigital.live/Zee-Bangla/index.m3u8",
                                    img: "https://live.bdtype.com/upload/tv/Zee-bangla-hd-tv.png",
                                    category: "INDIAN"
                                },

                                {
                                    name: "Zee Bangla Cinema",
                                    url: "https://smart.bengaldigital.live/Zee-Bangla-Cinema/index.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEi6FlTsvrXjTEVaM9-FqJFiq8LnKv_nLEBRqcCT0aJKPKRv5BWDvrtpheGSr48OClsGcPO0KMuki-_RxWBiVcBYGw_Cuv0tz0GeyKz1bdaVDAEPNp8C3ivXLQs066bbz0VeJu7j6_0bagJwzDtzBRmUxP2mE5_-7vwkNchPqvzap3Ot2J2Ds11G0TCFx1I/s1600/ZeeBanglaCinemaPromoDesign_1_copy_900x900.png",
                                    category: "INDIAN"
                                },



                                {
                                    name: "ColorsBan",
                                    url: "https://tvsen5.aynaott.com/u3LkNQ7UHhFX/tracks-v1a1/mono.ts.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjRxTKw7Waf7pE-u1c7DLQTjWyHZZEtkpbemaiDLQJIA89m6Bq9FDAbX9hUwVNMmx9FTJvyJoWIvVg_LNrXY8mWKlNSbNVp6yZsGueCW8o-D0_vAYG1ff7R7taaWn0eYuvXwAtrqst680Fi8n74hRFdCF6xYuXZNVDqK9AYdRq5npe-DkoBulPDp1ReUog/s1600/ColorsBanglaLogowithNadimRazaTV_copy_900x900.png",
                                    category: "INDIAN"
                                },

                                {
                                    name: "Star Plus ",
                                    url: "https://live.dinesh29.com.np/stream/livetv/starplushd/master.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEg_UGdDtFb73MGytBLgMhA_15mQ1E7f9ta31UlKvlSniZuiDyP9z7RmdqDlKArj4jhfNdAntyieSTL7jmdVoGhrdydtgw8LqQPkJZRtwXXlzK71MkFWNqsJZxHhs9pSsL-PbyDQCzqvQs7jka7X4tOiXoMn0woMfXBqktZu61v5vBHdIByxb768W1GiGFM/s1600/starplushd_copy_900x900.png",
                                    category: "INDIAN"
                                },

                                {
                                    name: "ZeeTV HD",
                                    url: "https://live.dinesh29.com.np/stream/tataplay/zeetvhd/master.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgYyGImv_rpC0iVLuNkew4sHa7YtjVoqsZuIC9PHjc0u83aK0kMCGLU3Swmugl-lSIFflY6VDG0sRHD4ApwNiqU6c78GnPkaalx0p8a9RALkrnNLupIx6HHCIXS35_ORY73Y8i-e3yNjgquAL_jZyRwvnc1dIAhMG1lWHIH1xQpmO4jXR0DF-esJp-uAK4/s1600/zeetvhd_copy_900x900.png",
                                    category: "INDIAN"
                                },

                                {
                                    name: "Sony MaxHD",
                                    url: "https://live.dinesh29.com.np/stream/livetv/sonymaxhd/master.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgqWyxx97k_amRgdFlwHpO4mmTFTXhpKAZVFqVEVtXlgmNJbsMTgugKs8Lrsm0ZFI1wWRBeif2y6gCr-_lS7K3scasyUO5hpMRc1oBbN_GZ_zfdpRJXsBJDyMhazU94Fsd8zuvAo7uZT7_-jNW1KiaB3HIjKQC87GCmRn3vG2BbW23luBBcVel7LxWaJ5M/s1600/sony-max-hd_copy_900x900.png",
                                    category: "INDIAN"
                                },


                                {
                                    name: "News 24 HD",
                                    url: "https://tvsen6.aynaott.com/news24/index.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgfTrH0SQA5hE5z7l_CO1jQ5G8I9sWjLSh_Nm-5nzzk_wS72L2GPgJbWRc7bU8soMftaj81rXvNBCdSCakDaiSwkuAdjcAJmx7f906uKX65RYyU_M5uS5-1Zh5bzFefaHcs-AA7FcVMU4olwpXNB5INYJrcc60s40MrPySZiQujIfZgUMeuIyXhUqPzjL4/s1600/NEWS24LogowithNadimRazaTVRepresentation_copy_900x900.png",
                                    category: "BANGLA"
                                },

                                {
                                    name: "Zee Cinema",
                                    url: "https://live.dinesh29.com.np/stream/livetv/zeecinemahd/master.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjokdI6y5cvg6iV2q8mzJe4Z-6LITgmiMdxkT1hzNnsSOHk9r9RBBGfFL9iyoVk3xysIG6Ncw1pnBQ81WrFHLj88pNcOqEDbni0gOaOFlKtUkTEe9zE9ruI6Azg1FyrLP8W1wsD56_MhR-j-m-FA7dD3h69MDCSPTY9-9liUzvL_JDLqMNk6AbANwVPNZ8/s1600/zeecinemahd_copy_900x900.png",
                                    category: "INDIAN"
                                },


                                {
                                    name: "Sony pix",
                                    url: "https://live.dinesh29.com.np/stream/tataplay/sonypixhd/master.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhN0vH_ILj7Qfjd7Ev3B2ccBXpq1Y2qeUde8lX7Ogy5jeVobDWEJZWlCsPtBl4kct3WZZJYKIHGQkV8QpZBDIVg4K8UMsloCBxN5092qVRDEpFhAXLS6VoBoD4_AkWViz779Eigf0hjwbGBVxFItdNhkKmEeK6KvPd5T-UL4-Nb-1cwp9pPrzEmXGjpFo8/s1600/sonypixhd_copy_900x900.png",
                                    category: "INDIAN"
                                },


                                {
                                    name: "& picture",
                                    url: "https://live.dinesh29.com.np/stream/tataplay/andpictureshd/master.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiB_-vLrG7jAr2gdX7GVshMmog4Sa3hpr0lb89ij4TeGgVOgzFnQCho48TfuYpbKFsV97cByAwMNsr0lLlgsSQ0MfL-WdDO5DcuyV9qTrVQHiIS2HJb6cdYth01RF1bcUW5BeG8JuQGhThbklqjXBQSpT-DEVaIoi4gy1DS1srpo2UPtcP50p1rzWalnQE/s1600/andpictureshd_copy_900x900.png",
                                    category: "INDIAN"
                                },

                                {
                                    name: "Movies Now",
                                    url: "https://live.dinesh29.com.np/stream/tataplay/moviesnowhd/master.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhNMXpGN4oJIT5_tNM7815CNIY3xQYErrao-Qn3ufIZsLYQRTLhWsV7IJ6qiwVpZSM-MDLWOdlTI-ly5pAidLtRYJ4QmG-mwqlL392-NkBXTwa9OT7BpAZi1EPO4jMCcnHTRqRh25CG8bMjpSLbbdYgDok6-4wgNOVEqbLtVFgXxQfq6Vs3Gau5JOkgVSk/s1600/moviesnowhd_copy_900x900.png",
                                    category: "INDIAN"
                                },


                                {
                                    name: "WWE HD ",
                                    url: "https://smart.bengaldigital.live/WWE/index.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhTcfQZ1Rjj4NkS6w2IORuV9cEMIkjP9xwryq81n9fv7m5GuLYrw-MECn1yi4sou3z8enPJNGVH3xMU8HPofLqiFNOrtHiVMzJqDPfBIeGiOTBfBXeOQFDGggXMGujZQUQj16ybn_iWQM95kV-c7iFWMDPqg6icd4dJdJzvyFDweHZm1GllpYb6z19uaLc/s1600/wwe-logo-png_seeklogo-368682%281%29_copy_900x900.png",
                                    category: "INDIAN"
                                },


                                {
                                    name: "Discovery",
                                    url: "https://tvsen6.aynaott.com/discovery_hd_bangla/index.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhWn4klBdX6KPWcHsz903jrFZtzLx8lsfoGCVE_L3kdf3dXJHF2DVMHduho9kUgw-ZwE4c1xE657s14PPn0XMJUaxmHhs2s3wE-f7UtBUVa52-gXT5LhogHH3X_7-gk7woT202QqeS8GbBAB68_MFQwMWjIpTKV1aVTaX-quz2nhb1yH7LD2tAz1Z1Gt8M/s1600/images_copy_900x900.png",
                                    category: "INDIAN"
                                },

                                {
                                    name: "CN HD ",
                                    url: "https://softbd24.com/new/toffee/?play=57bd9c2493c1",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjwZmWCqIUZS3SxKgQXx1Wfrv34HnH1OGc8IWfPXs3wyjG8jEvlFBTM2Wkjmqe73Mt_K3_i231Lviblz0qEnkP_hDZrcnbjMkI-lVMg9NjTdsJ0I_vUW5x5rJpNjx7-KDyQ_FeITM9gj6dpJ3w-519LE7U1xwp9LNMyj5eKvpi8UHZVBNMRXp2GWymru8c/s1600/Cartoon_Network_2010_logo.svg_copy_900x900.png",
                                    category: "INDIAN"
                                },
                                {
                                    name: "9xJalwa",
                                    url: "https://live.dinesh29.com.np/stream/jiotv/9xjalwa/master.m3u8",
                                    img: "https://live.dinesh29.com.np/logos/jiotv/9xjalwa.png",
                                    category: "INDIAN"
                                },
 
                             


                          

                                {
                                    name: "Nick India",
                                    url: "https://live.dinesh29.com.np/stream/livetv/nickindia/master.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjvJLdB7fGCI1kTCj1zrasapUGggeVDeAWgVrUUDEUUof1K13m8ZKdYkztAP6qKwtnzz3pBxpAe8wZsR4yYXagDlJ_3qJARJ1LGzVZUS-cWaQvnuobqHZHuZpM4qjzKLVsxxDO8vFEwJeKCZgIJF8rSJpqzb3Ne2FmiDJoLYu722A0pX1P1UzCIWgw_70A/s1600/nick-india_copy_900x900.png",
                                    category: "INDIAN"
                                },


                            
                                {
                                    name: "Star Movies HD",
                                    url: "https://live.dinesh29.com.np/stream/livetv/starmovieshd/master.m3u8",
                                    img: "https://www.nicepng.com/png/full/213-2132991_star-movies-hd-logo.png",
                                    category: "MOVIES"
                                },
                               


                                {
                                    name: "Movie 1",
                                    url: "https://cdn-2.pishow.tv/live/1459/master.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEitWsg_yYy_couXdo1TYesML2Mttifc2K9n-UYa7EMdI1pXY6Ukq6JYcwpOseHfnvYAQqLS3Ai5aDahVxgMWMI6K6VO_Rurq3Kgq0PEzQD17e4EJS84LxYyIzh9Koa4o5oDzZD5yR-CUoVHNwQm5voVtqqDVGI2xLkpwqt_Eme0Uc3eUD1XL0PhmbIR8c8/s1600/GoldenRadianceandBoldText_copy_900x900_1.png",
                                    category: "INDIAN"
                                },



                                {
                                    name: "Movie 2",
                                    url: "https://cdn-2.pishow.tv/live/1461/master.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEitWsg_yYy_couXdo1TYesML2Mttifc2K9n-UYa7EMdI1pXY6Ukq6JYcwpOseHfnvYAQqLS3Ai5aDahVxgMWMI6K6VO_Rurq3Kgq0PEzQD17e4EJS84LxYyIzh9Koa4o5oDzZD5yR-CUoVHNwQm5voVtqqDVGI2xLkpwqt_Eme0Uc3eUD1XL0PhmbIR8c8/s1600/GoldenRadianceandBoldText_copy_900x900_1.png",
                                    category: "INDIAN"
                                },


                                {
                                    name: "Movie 3",
                                    url: "https://cloudfrontnet.vercel.app/tplay/playout/209612/master.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiulOSH52HU80bFDkGLFLyE1Z4fHSK8LrH59TckacjeLkvmxgyXxaXwPlJCKQJlkqvhZ-VMiatsJq8yAXRf3jyzs0HwYtXW4cACHsXT3Dnzlus9jn-4aW6wdcwbdFBNn1VLSNNwdAYnMA_c-7xEyfgwAp5NjcZUh8g_dV_Z9a847dYCys_7P4sdZn-6GbM/s1600/ALLTimeMOVIESLogoDesign_copy_900x900_1.png",
                                    category: "INDIAN"
                                },


                                {
                                    name: "Movie 4",
                                    url: "https://cloudfrontnet.vercel.app/tplay/playout/209627/master.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEg5R4GGvdkgQHjuiGaHqGKEJ4m2LFlBhmFoJGl2_2DqThwYzd7YalwU18bTEqh2jdqQMqEc1Qz9dZBwdfoRvPKcKaxqPZzsH3jrjgTiO4OAMM68x-RMsidon9OELn_Gg3VzH9rMZaCS-dl6ENhMAq3hkxS04XBWueLQJVClD2xuPvvl3I07LyjArMux3yk/s1600/KolkataMovietoneLogoDesign_copy_900x900.png",
                                    category: "INDIAN"
                                },


                                {
                                    name: "Tplay Hindi",
                                    url: "https://cloudfrontnet.vercel.app/tplay/playout/209592/master.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiZ6YnrOMoPXyMggJRK41rwFoveWp2o55YS-f8HhsHyNdlqvjiE2RHTtROav04BOhPR19nDy9JxvF8E8BeJ92JIrC-J84jP9oVM9phUEm8E_8LI8NyNymbUaffKZ2iailw6sbiRMbIIcCE2dHm2BSJXWIYfUlsfEACuvppzNzNdlFvzYltTL1cgU28plSQ/s1600/HindiSongsLogoDesign_copy_900x900_1.png",
                                    category: "INDIAN"
                                },



                                {
                                    name: "SunBangla",
                                    url: "https://smart.bengaldigital.live/sun-bangla-paid/index.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEi7Stw22VLpLbD1W3HYcGVqw7fx5RMW0Z5fmx-nNnasDfLPHupMMjf0tbK2E-82qiPE1oQFb8pptlLX7912u0oPhPiH_7Akm2zI_OqbZmrH6RAy-yMIZa-oy3RPXm4Xi6DPqbll6M3B3g_6EWKb1E1Bt2nIU_gEnMyTlh_wBlN1R9I8_a115V2psHrS3Ro/s1600/SUNBangla&NadimRazaTVLogo_copy_900x900.png",
                                    category: "INDIAN"
                                },






                                {
                                    name: "9XM HD",
                                    url: "https://d14c63magvk61v.cloudfront.net/strm/channels/9xm/master.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjiGC0wT3ja7ZcbTl7yGpm4X9BMtfiCTsejIn3kDk_KKP2-Vzd6mQJD0QquLDSCSAlg5HrRL9lNYawNR51toENqWBzTz6EFX7mNlfMS5T3_-K6KD__yxtr3rnsMX83pnxUGMGngPupcNltt_dD324D-ZNfaFJmy-7dshVn0kTFbAWoX80g7_id0XeXlVkM/s1600/9XMLogowithNadimRazaTVBranding_copy_900x900_1.png",
                                    category: "INDIAN"
                                },





                                {
                                    name: "B4Umovie",
                                    url: "https://d3kdywbtdfbp9z.cloudfront.net/v1/manifest/93ce20f0f52760bf38be911ff4c91ed02aa2fd92/dff423e0-3c82-46d6-9ecb-3baa96b5694a/cd1f59d6-9b5d-43f0-bfb2-6ca9edc99f27/0.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjVJk3M031mdsFJjCqotDhNoO3PuCMeZrps1FLTTTuZMe8NbkqxVowJYd-gv4AFr0mK8VZ_xKogEpUe8c6_76ExP0Qkpqv02Z6ZEOSxhVFKIVwtFQQ7-bZiqaXGNiVVFxSBzZNP1ZHL5fedBTLbhzgJzW803OIIe14_kUC8QyyT4fhmy3ukJFIAFexuNUk/s1600/B4UMoviesLogowithNadimRazaTV_copy_900x900_1.png",
                                    category: "INDIAN"
                                },




                                {
                                    name: "B4Umusic",
                                    url: "https://d3kdywbtdfbp9z.cloudfront.net/v1/manifest/93ce20f0f52760bf38be911ff4c91ed02aa2fd92/dff423e0-3c82-46d6-9ecb-3baa96b5694a/4598c408-0e38-488c-9b64-fc845d1ea2b6/1.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhG5F5bkCl1_7ULXAvL7sklW0LzX-yOckVOWBDcOrLqQI6UleLY6zkPAgnYuYPvqq4Jmj3VLcWMUPeWMzXl-3OqhwZL9BskRHJfDErzFWYhsQaiZEuzuz_sL2lFnYjIycACxS7OfUbs7BjhXgOAjUGdvBfi2oTLYXpsD_GE45k79V0qr_i1dB0JF5QBnAA/s1600/B4UMusicwithNadimRazaTVLogo_copy_900x900.png",
                                    category: "INDIAN"
                                },




                                {
                                    name: "SangethBAN",
                                    url: "https://cdn-4.pishow.tv/live/1143/master.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEi4e2y8s32kBZDRrFz7XO1OdJCzcwjeQSXb2Ysvd9Z02WheXXM6a7aIpd8OvYmuOSa235RMKodgF7pSdb_L4EQdTqXAWwKRoixrfZYPVR_GdjhXh3gmjmyyrUS-X1pyjrzq1Okle7naUBt9QFCC0sUa2897Jk_6CwduvH_wyoo_g9gJr6AFpUSFZySalRw/s1600/SangeetBanglaLogoDesign_copy_900x900_1.png",
                                    category: "INDIAN"
                                },



                                {
                                    name: "ZOOM",
                                    url: "https://app24.jagobd.com.bd/c3VydmVyX8RpbEU9Mi8xNy8yMFDDEHGcfRgzQ6NTAgdEoaeFzbF92YWxIZTO0U0ezN1IzMyfvcEdsEfeDeKiNkVN3PTOmdFsaWRtaW51aiPhnPTI2/zoomin.stream/playlist.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhPtATyVD6zIHcpWvMlSTz3ZxGJ_7FeK0eLHBvFH7xjZ8fAsdiTghut6akxYyIto-0rMgko3MG9KV7WR7aLVUgJDkfZiN7uTGcuSSf8QBwYKQn0q8H1n3f61LCUHwQsRD-bmi4qsjYHQYKTew6oShZhneanG-iiut4CejY32oASHzd5-iUSJ0LYoKLMYjQ/s1600/BoldMinimalistZoomLogo_copy_900x900.png",
                                    category: "INDIAN"
                                },



                                {
                                    name: "ZoMusic",
                                    url: "https://livecdn.live247stream.com/joomusic/tv/playlist.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjNpQi9_0P97bAywoLekW2eUBO9OKkCFu3OJw0HPSeYENjhp6Dkntq2Nu2txW40QsAORP330ZK6PRpTezK4mcx4qTtpBoHOHkGkD_YQ5cTlWkIjXsPsHw8QXbHsFQQZXQTRkexNlQOUNkGx-oSZXdKSJxdJ71S6u4qMBCjqydZMASaF2DrXN-dWYmBOmcY/s1600/ModernLogoDesignwithSpeakerIcons_copy_900x900_1.png",
                                    category: "INDIAN"
                                },





                                {
                                    name: "Masti",
                                    url: "https://sabliveyupp.akamaized.net/v1/master/611d79b11b77e2f571934fd80ca1413453772ac7/sablive_https/mastii/playlist.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhHslsenwNE5covP96X1eL2TeY4q3qb5S3ee22-MihDxRZqUg2R5gYV9FDUL5EzSjutasFEG5YEvprSBLGzpIg4RqnkRJ5OXQCNgTqXtMIFxq7f9FnWDlv8KhMa50ZZPBqrj5w_2bVkAa1bUFtmZ2wM-66Vn0B6GUINyVUrE4wGFpPbvPqA0rxn3KCk7iQ/s1600/AB-MASTiiiSABGROUPLogo&NadimRazaTV_copy_900x900.png",
                                    category: "INDIAN"
                                },




                                {
                                    name: "E24",
                                    url: "https://live-e24.dailyhunt.in/eternowsa/live/amlst:E24_,b256,b512,b1024,b1824,.smil/playlist_1824k.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiRGXgSIoPFvTJK_3B3viq74PklRMz3eZsoNPYX2zh583yeO5xUSgab_Mk0FUAy7zhH88jYOZLvjdpa8S8zku1xneZgpR93yj10i-55c1W2F6HHbzvGFdAqLxXvrm3K2xFsXuKdwZZDyUIFNQSeIc24rw_6AZa_MMW5-SRTTyKcKdVOP4aL7YfpGo9X7dc/s1600/E24LogowithNadimRazaTV.png",
                                    category: "INDIAN"
                                },





                                {
                                    name: "8XM",
                                    url: "https://vodzong.mjunoon.tv:8087/streamtest/8XM-131/playlist.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEj2tvKILoKF6fHfN8VzPnHasV7i3-NErg23dZvri9XzOcNDrSC9YmMaYDGxIVqwekxWREzJ6eu_nKm5Njz4HHSq4g8xwItvw91PU65-GnQFFn0nBtFyz_QiJW7XKpFnlkkEr1VuFCehfnZYjbVXeCzdpedXflY-jDQiItgOfAQpabbUTShaWTztIxzAeR8/s1600/8XmHDLogowithNadimRazaTV_copy_900x900.png",
                                    category: "INDIAN"
                                },




                                {
                                    name: "Bollywood",
                                    url: "https://d35j504z0x2vu2.cloudfront.net/v1/master/0bc8e8376bd8417a1b6761138aa41c26c7309312/bollywood-hd/manifest.m3u8?nadimrazatv",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgn6OM1RPMqODMyu7zr0A8RO7Iho92EDbPEH7vcm4mN00pGe_3tfmxUPLq_ykufvE2RahIvma3OAtz4QEyRyYeu-ydz75KSEc7ZDVjMfoiYA8IT4bVEjjlMPe4EPnUgllQw8dDXFhbcJGip8hj2HbGlpHPzWBet6sP5yTWfFFE1guUrL2gCTFTVYypcR40/s1600/ModernLogoDesignwithBoldTypography_copy_900x900.png",
                                    category: "INDIAN"
                                },





                                {
                                    name: "Classic ",
                                    url: "https://d35j504z0x2vu2.cloudfront.net/v1/master/0bc8e8376bd8417a1b6761138aa41c26c7309312/bollywood-classic/manifest.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgn6OM1RPMqODMyu7zr0A8RO7Iho92EDbPEH7vcm4mN00pGe_3tfmxUPLq_ykufvE2RahIvma3OAtz4QEyRyYeu-ydz75KSEc7ZDVjMfoiYA8IT4bVEjjlMPe4EPnUgllQw8dDXFhbcJGip8hj2HbGlpHPzWBet6sP5yTWfFFE1guUrL2gCTFTVYypcR40/s1600/ModernLogoDesignwithBoldTypography_copy_900x900.png",
                                    category: "INDIAN"
                                },





                                {
                                    name: "Cinema",
                                    url: "https://live-bhojpuri.akamaized.net/liveabr/playlist.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgchyphenhyphenntXTihziGy-H7BehkEiQZE5Cclggwy8X0L0VDeeXmzgUnpryXy9lCKuycienzA3puQDhnG6WN4-f1T-ojkJjWYAaDRS1456xbZ56yjihnI7P8g9os8J-F3b25v1XkiwAcsQCuVfIQE0JL_4cMW3DVZFdKCn0alLIyoBpQGSuS3ul4PQtJfrH-llis/s1600/BhojpuriCinemaComedyLogoDesign_copy_900x900_1.png",
                                    category: "INDIAN"
                                },





                                {
                                    name: "Ropushi",
                                    url: "https://cdn-4.pishow.tv/live/1039/master.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjsAge35-PXO_PGO7CUSiyrE_MeEHtHzRr_GYz7ezZUCCUi5_s5iuoR7-Mrv1zC4usgnDDQzuarRdNTc-ntk7XXI67ueb7m4hP37aIgVafFrkZP3jCwj7jiUQ9BnoVRRq6hTPW5sX10rmQwuq-Obhyphenhyphen-bDauwMOAEvKOwQu3k413WpWUJ_amFYJTVIrE8ww/s1600/RuposhiBanglaLogoDesign_copy_900x900_1.png",
                                    category: "INDIAN"
                                },





                                {
                                    name: "Depot",
                                    url: "https://byphdgllyk.gpcdn.net/hls/deeptotv/0_1/index.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjGNArpOiSA0kLxr9IgoJVduSywxgQI_ulhqjMk9qQevNJ7OtuCGBQlhtEv5aHPm0pVqKvrQ9-gIa7BPtIeP0NxVnYdKJ3NrT70THgXcalrGdF0iDb_S4ucJd3sVi98XiC8iXrQDsr7zeV-XeeuwGt-9Hzw4IHZLlqJDjjDwpPCTsb1FEg1q2_eqwxDtgs/s1600/NadimRazaTVHDLogoDesign_copy_900x900.png",
                                    category: "BANGLA"
                                },



                                {
                                    name: "Rajdhani TV",
                                    url: "https://iptvbd.live/rajdhanitv/1080.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEivjCIfsHlO6Cg2v92-BpWx-f2UPjmmQxqRLBgAC_god5pvJyuyQIhXXWaGrpEg-11PrvQ312X6S0Npb-tWGfuCloQdn5O7sGbpNgLD2WxdPuqyDXELGr8TCSHnR7e5LMmnDHwApsm5MUob_Z0urgfY7wuHoHFdPY0M-a_nJchKyzX6q68mmLhF8uKAWVM/s1600/Rajdhani.tvLogowithBengaliText_copy_900x900_1.png",
                                    category: "BANGLA"
                                },









                                {
                                    name: "Ananda",
                                    url: "https://app24.jagobd.com.bd/c3VydmVyX8RpbEU9Mi8xNy8yMFDDEHGcfRgzQ6NTAgdEoaeFzbF92YWxIZTO0U0ezN1IzMyfvcEdsEfeDeKiNkVN3PTOmdFsaWRtaW51aiPhnPTI2/anandatv.stream/playlist.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhP4yzjaHbB_viVYzig24kwzZ3cOTY6R9CknIPn0LGyFA3tTo7glIhXAVTA6asHNPJButeAs_QwZZzDn5KoVbhUWrmqjBFmhw-4z0gr_jjMuL5Gk5tGlsJLQhwj6dj75iYckRkaxiitEvm1o72ncn9MpAYp3f4huRowa_xPW3KZbmpQUjK4yesK7_QI2Yc/s1600/AnandTVLogoDesign_copy_900x900.png",
                                    category: "BANGLA"
                                },











                                {
                                    name: "Movie",
                                    url: "https://app24.jagobd.com.bd/c3VydmVyX8RpbEU9Mi8xNy8yMFDDEHGcfRgzQ6NTAgdEoaeFzbF92YWxIZTO0U0ezN1IzMyfvcEdsEfeDeKiNkVN3PTOmdFsaWRtaW51aiPhnPTI2/moviebanglalink2.stream/playlist.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgQ-dPX0ds4WEGuiUNal8Rs36klrLdjPgl9mbUctBWr8gwcCjqlcUvqCPVxGH1REQKDeqGNaZT0_N2KTbSEYBsTDvjphA4ZpTm6YYQrOiM1zlU9CD7edgCrvvavUBemCMTr5Xu36OTLzkQqUMmn0nTzwdHDJwFaqm9uuycE93iVsUToPPhgopUvYkpr4JY/s1600/MovieBanglaLogoDesign_copy_900x900.png",
                                    category: "BANGLA"
                                },





                                {
                                    name: "MYTV",
                                    url: "https://mytvbangla.com/0.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgfvUemICDmDqbQrkgHWWsOEaD6ktcAlxKkWBoj37tcHx70h6-ay3tEnJpQT8z31IarPnQp9x9x7oV5FCx9MFhLAtjnzDejK_D-dVbGk9Qo8iNnJ1LYsYDU3vAGjy3lgXxU8Iw8wreNa2FXlfyX56-bFWhgrdz-I5ZbXcCR4NzQYcJZnxVS-QijC3GUfHE/s1600/ColorfulDigitalLogoDesign_copy_900x900.png",
                                    category: "BANGLA"
                                },





                                {
                                    name: "Masranga",
                                    url: "https://tvsen5.aynaott.com/tK2BNvT68fHZ/tracks-v1a1/mono.ts.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgcSZLFdCOhXu73YHoLQY-Cqd7LKQoK0d-4K_HGPbvulwFaHZ6KQPQv3W-QdXJ82RXG7SWK0EWrHKU4IHkFoZy3LSfrelSZo3GzeYvfkqQS8RKJ9HpYLqwmd1vVKt7QdLp3b5azDXCklBj9RnLtMYRo0QSKz0gVKWQvyeB9wUawK8TCWTJWJlandz4g3-8/s1600/KingfisherLogoforNadimRazaTV_copy_900x900.png",
                                    category: "BANGLA"
                                },








                                {
                                    name: "ChanelA1",
                                    url: "https://iptvbd.live/channela1/1080.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiAbqwmkTqJ6hZgIO_5cM_QVycG-R6f7g13VnGDhF1TDIe5bWHUOmDPiZOwtSojCOCVwa7oT61RRML0s3f1yYaKxdc12u8fmH8wHSx_aVXDYKMiIA9QEkHwQeMqwSyabJPNLuIV_7UjbPymQGXF_ETodINfLdsCafQhh0jjeRkgqXz6eXU3md-2rhPzxxQ/s1600/ChannelA1LogoDesign_copy_900x900.png",
                                    category: "BANGLA"
                                },











                                {
                                    name: "jamunna",
                                    url: "https://owrcovcrpy.gpcdn.net/bpk-tv/1701/output/index.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhEKm4fcnyVheoCCyaMh3RqcF6K5rXsqypr7wYPpTcnso3UndbODp34kuXI_8o_jCL7fGrmqDdm_4h2MVKFfuLQOyJEt0imoL8jTPSF6Klb98HR-xqKgEl3WwU3ZaASw8UIcTg_JcAUIjb41vxDa93MgYkpZaTIEmlbZQSp9um5XhT8jTEcTRZlu7gcTHQ/s1600/JamunaTVandNadimRazaTVLogo_copy_900x900.png",
                                    category: "BANGLA"
                                },




                                {
                                    name: "Chanel24",
                                    url: "https://owrcovcrpy.gpcdn.net/bpk-tv/1703/output/index.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgEHfy4lW6fCl0jInoyzXbQqumBWkqoOOJzlSUMA7g8K8Sh_X6fyDhq03eBy4UJCNvYRwsT2YaGYa1kaNfIHUjDMRqnNNelg9YanS3T5MRtmJfFV9Bcn9CMvB9Y-bCDdei2lil2MClmtVGC4-feZn44_FcHCLchgxR8ucrwh2OsWuXxvHJksYtKBdqLpXE/s1600/SphericalChannel24LogoDesign_copy_900x900.png",
                                    category: "BANGLA"
                                },







                                {
                                    name: "Ekkator",
                                    url: "https://owrcovcrpy.gpcdn.net/bpk-tv/1705/output/index.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgMc_YC_S98vXV1Fd6-OeHww7gLDjVAF49ZGvxJPawse_8KQAalt4TFKkkGAhBv_kk9THS_wUoKWjHsEk5bv2h3K3cmC04DTHJOrMRrW_krr09FCAePo7XN8X5KspXS2s0icqcrE9-xszLTJF3-LbEHaw4dzVEzkyA1IXQKlEDqUFi_sjzTs4PRT_7IVTE/s1600/EkattorTVHDLogoDesign_copy_900x900.png",
                                    category: "BANGLA"
                                },











                                {
                                    name: "BTV",
                                    url: "https://owrcovcrpy.gpcdn.net/bpk-tv/1709/output/index.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiYJp-BvjjLu3G3ToDR2jgittB-tzF4QU7bDqxvcQJBx7cQixHbUBdkZoepSWbJqs8WZH2n8VvdPfXaCHmVFmBc6jd_IEfl1TXyfw41EbCnAfs6XFBYyiZ8rHjfTmDgAUCNCIc3BN7Eg4VLE1pCWA6I1YASG_6oEMLLreQuZ8fSI4aIlYWWFJ9m5CG2lys/s1600/BangladeshTelevisionEmblemLogo_copy_900x900.png",
                                    category: "BANGLA"
                                },









                                {
                                    name: "RTV",
                                    url: "https://tvsen6.aynaott.com/rtv/index.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjEg3lEDJrRmU_tIyYjkATU0hW_i9QODvn_vOhKl70CIEpK9McsFlQQUj3iqQofqJAapD1ABg-TDDd3oD_HWLZaMf9hpuyszujG5Jtd5jwYqhcWmVmIoNc1fPErjmYa21rPynE3YyIMyjhegKoEOfgII8jrBPV0896krHOIkNZeCKlQ9STnZSRyhd8yngk/s1600/ModernRTVLogoDesign_copy_900x900.png",
                                    category: "BANGLA"
                                },











                                {
                                    name: "SATV",
                                    url: "https://app24.jagobd.com.bd/c3VydmVyX8RpbEU9Mi8xNy8yMFDDEHGcfRgzQ6NTAgdEoaeFzbF92YWxIZTO0U0ezN1IzMyfvcEdsEfeDeKiNkVN3PTOmdFsaWRtaW51aiPhnPTI2/satvoff5666.stream/playlist.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjcr__Akekl5kx8CGId46t6K2mjsXZxN-xPCb98S0S0XS5GHsgyGBYZ4S9Hy0IDdUgec1cNcCtuRHk2FJceCrgV7xencCWm7Z_Vu9kUcbB9HZoy9TWucHsOCBGF87-7hiNIprDg29R3EBYPspAk6Wao7eQJZqVkIKYcCKXx8pC_y-ERKVk4MZulKmUdSaA/s1600/SA%E2%80%A2TVandNadimRazaTVLogo_copy_900x900.png",
                                    category: "BANGLA"
                                },












                                {
                                    name: "DeshTV",
                                    url: "https://tvsen6.aynaott.com/deshtv/index.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhfnfTILr2F6VWubCw9m-9BJqEWfzuWDN8_XNuYNlFZko8yG7ZYPmQdpIKZ7mnDJezB_fF5FX_XxtDEp286Gk4g_iZX6v84I0g8AbVezdDIBalW_27YU-KtOYsrH30H2Qw7Wy24NHUoPdYsk784H3R0CnakTee7hJBanbavRVvpIfu2YJq0Nmr7brJZuT4/s1600/DeshTVLogowithNadimRazaTV_copy_900x900.png",
                                    category: "BANGLA"
                                },









                                {
                                    name: "AsianTV",
                                    url: "https://app24.jagobd.com.bd/c3VydmVyX8RpbEU9Mi8xNy8yMFDDEHGcfRgzQ6NTAgdEoaeFzbF92YWxIZTO0U0ezN1IzMyfvcEdsEfeDeKiNkVN3PTOmdFsaWRtaW51aiPhnPTI2/asian-test-sample-ok-d.stream/playlist.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgaD1OgyFg8PGw1acgGq3XT2I8r3KyJ_BHoOv0PuuAD43c3bvBGOJHcCj_029k6i_boNDElRNAlmMwZ0VfyUX9sfbQ52P_SfIWKI9Ai30f9KqwMLFUmOpKics6jaUtY3tCv30HM81IyxseN9v6g8cNXsotwfAFdgjFc8dQLS6RXzBalYSbiYMKWG52HsNE/s1600/AsianTVLogoDesign_copy_900x900.png",
                                    category: "BANGLA"
                                },







                                {
                                    name: "Ekhon",
                                    url: "https://app24.jagobd.com.bd/c3VydmVyX8RpbEU9Mi8xNy8yMFDDEHGcfRgzQ6NTAgdEoaeFzbF92YWxIZTO0U0ezN1IzMyfvcEdsEfeDeKiNkVN3PTOmdFsaWRtaW51aiPhnPTI2/globaltv.stream/playlist.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhTSXN8JU_FEfj-xZs6-6xpTcpvt_82Oa7ChvEoG2H_NFpSKIsU8f4DvbGvgs1vLh1S_atRl-_4iJOtFElyJE1nX9S1yk33s392c-gz05EnR66IL99WM566VPYP0K8aVmJ4rc2tpbfhm8UgWVCVE9USI86LBK9k71yFU59sTL61VtLoEOU5GoNxSfmx-p4/s1600/StylizedBengaliLogowithCoin_copy_900x900.png",
                                    category: "BANGLA"
                                },





                                {
                                    name: "NTV HD",
                                    url: "https://owrcovcrpy.gpcdn.net/bpk-tv/1716/output/index.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgBL8dw8QObd_kn5unTtrFhvOO22HLp-3FtFQViBELpTOZWSI1zObrT03qUujhMO14BDlZY-p-aVidJxIW3t7aNiCuEH66oCVsa_J74GuGQt54rLOKguW_wSCtYt8YMcyPjPq_ChDaxy-mn9wFlRS822YrzGmQm8kbIOQLLNhIgnrVqms-Grc3-mljpI6k/s1600/NadimRazaTVLogoDesign%281%29_1_copy_900x900.png",
                                    category: "BANGLA"
                                },



                                {
                                    name: "METV",
                                    url: "https://iptvbd.live/metv1080/1080.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhlP74bV_ECM0FtB3ekan2mRhpBFjAg0vF_8tvAQnjcxpU93StSo87YC17Iv09Z4DY7Mit9Iu2uLlvx-hyqorOLSmnPjTbuV1ZFfHxMU-gJFGNtJhMn162b-JwHUkRDf1ke96aYwc3u9pvTvfH08UCKlnCUzdu_WDkYdsYKQ1mf071EsZ3Z05kxFL7BbT0/s1600/MeTVLogowithGreenTriangle_copy_900x900.png",
                                    category: "BANGLA"
                                },




                                {
                                    name: "AmarBangla",
                                    url: "https://app24.jagobd.com.bd/c3VydmVyX8RpbEU9Mi8xNy8yMFDDEHGcfRgzQ6NTAgdEoaeFzbF92YWxIZTO0U0ezN1IzMyfvcEdsEfeDeKiNkVN3PTOmdFsaWRtaW51aiPhnPTI2/amarbanglatv.stream/playlist.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhifuuLKqcaibWpGoKTyadOvMlaPzAvateCAUnOz5QXVC8A2Yf3X4zvRyRrJZDd7YJMaABHGQ3ru4itjhE1yxF8gJxYzNjZ0PosjnUGm86kX5Qhn0uuvn0FzCFl_B4HioyFc6JJUYCEBqt8QFgXXTyH0GNDoA81C-6NWN9eSNcg5A_vTEGDP-HvXIYp-QQ/s1600/AmarBanglaLogoDesign_copy_900x900.png",
                                    category: "INDIAN"
                                },






                                {
                                    name: "PLUS HD",
                                    url: "https://live-stream.utkalbongo.com/hls/livebanglatvstream.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEir8DIISD_3Ay4E2H__HTS4VFP7VXskYcIgkufU45epPzAFDKObL2D_p6mOal9B0RJpyaiA3feJuyaL8yvd0x-2nykRjc1pZPwT_aAGwmwFb4bEJf8oVDgty5NF30gzWlwHvh2P2c49pP2P8383ili_yboK1uSyqELcZygHTpSwru1VeK0mMwceugT5QLw/s1600/NadimRazaTVLogoDesign%282%29_copy_900x900_1.png",
                                    category: "BANGLA"
                                },





                                {
                                    name: "Global",
                                    url: "https://app24.jagobd.com.bd/c3VydmVyX8RpbEU9Mi8xNy8yMFDDEHGcfRgzQ6NTAgdEoaeFzbF92YWxIZTO0U0ezN1IzMyfvcEdsEfeDeKiNkVN3PTOmdFsaWRtaW51aiPhnPTI2/Global-tv.stream/tracks-v1a1/mono.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjTAmFFwQH9uvL61r5TMyKAR1rcy3_9rzI0H5jOV842nF7F9qC6qoZKooUMXGsAo_Tbic189L9I51t2EEDDAJqbUP672AoaR0DqjiiGi_IJlvXzh4186o8-02HRGwbtij-AfhZikCjRqeScGnlIg82F3jmtM3p5SM8RF1mJczXBqff-SrWKe8poPzHTFzo/s1600/NadimRazaTVLogoDesign_copy_900x900.png",
                                    category: "BANGLA"
                                },




                                {
                                    name: "NRB HD",
                                    url: "https://app24.jagobd.com.bd/c3VydmVyX8RpbEU9Mi8xNy8yMFDDEHGcfRgzQ6NTAgdEoaeFzbF92YWxIZTO0U0ezN1IzMyfvcEdsEfeDeKiNkVN3PTOmdFsaWRtaW51aiPhnPTI2/nrb-eu.stream/tracks-v1a1/mono.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjeX0fMKpc_lRfrT6qTXG0iK7ltwilygRaZ61fPX_7T7RHkjdwTIaYDHWSMRVFez2eBnGGnAM3logWZ9f7r7uJGEZQQZfjb3hydOkm9Q2FEULaQHhxJkJqUrOA8xCxdnHEYTNhNoUSXONX48zDINAFHI80edoaKzFHO2TQg4N9ojnbp-Ae3eCX_XuQ-ZOE/s1600/NRBLogoDesignwithColorAccents_copy_900x900.png",
                                    category: "BANGLA"
                                },



                                {
                                    name: "BanglaTV",
                                    url: "https://tvsen6.aynaott.com/banglatv/index.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgu7qaSv7IEHayKrmburt8ggOGjNg7nujQ9du3tAs2v0d0cvUnJomuRA-BKaXoqvm6xkKjRDa9vrjVNPp-9-FaEeyzepvfeW0cymNwtLvzLozOzE5v6Vldip0wtXKCq64MZnN1YkipigPqTqe2Uf0aFRIOdY5GcLqDknFi8xAyqjpNz-AXBqkPTeX9nxUo/s1600/BanglaTVLogoDesign_copy_900x900.png",
                                    category: "BANGLA"
                                },



















                                {
                                    name: "Somoy",
                                    url: "https://owrcovcrpy.gpcdn.net/bpk-tv/1702/output/index.m3u8",
                                    img: "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgYCgcsRHgXpA0wPwSYvoTEbPdVaxO50Q8nF02WzdMlBNxpcHgDhUmEJ3qb-yqIUGYTIecb32wJECeQEs7bJ9zVONg-26DIKkjvESJkeSKYe1qtXkYt8Nz4jE85EFkWUQbHk7oRj_1QgOLQZqxZEbigDfrq8CG0rKoNXVgWplPu8Rw4or6sMhgIQTXIWZE/s1600/BangladeshiNewsChannelLogoDesign_copy_900x900.png",
                                    category: "BANGLA"
                                }

                            ];


                            function loadStream(url, startPosition = 0) {
                                if (hls) {
                                    try {
                                        hls.destroy();
                                    } catch (e) {
                                        console.warn("HLS destroy error:", e);
                                    }
                                    hls = null;
                                }

                                if (Hls.isSupported()) {
                                    hls = new Hls({
                                        autoStartLoad: true,
                                        maxBufferLength: 30
                                    });
                                    hls.loadSource(url);
                                    hls.attachMedia(video);

                                    hls.on(Hls.Events.MANIFEST_PARSED, () => {
                                        loadingOverlay.style.display = "none";
                                        video.currentTime = startPosition;
                                        video.play().catch(() => {});
                                        updateQualityMenu();
                                    });

                                    hls.on(Hls.Events.ERROR, function(event, data) {
                                        if (data.fatal) {
                                            hls.destroy();
                                            hls = null;
                                            loadingOverlay.innerText = "BountyTab &#10060; Failed to load. Try another channel.";
                                        }
                                    });
                                } else {
                                    video.src = url;
                                    video.onloadeddata = () => {
                                        loadingOverlay.style.display = "none";
                                        video.currentTime = startPosition;
                                        video.play().catch(() => {});
                                    };
                                    video.onerror = () => {
                                        loadingOverlay.innerText = "BountyTab &#10060; Failed to load. Try another channel.";
                                    };
                                }
                            }

                            function switchChannel(url) {
                                currentChannelUrl = url;
                                posterImage.style.display = "none";
                                loadingOverlay.style.display = "flex";
                                loadingOverlay.innerText = " Loading Channel...";
                                video.pause();
                                video.removeAttribute('src');
                                video.load();

                                // শ&#2497;র&#2497;ত&#2503; পজ&#2495;শন 0 থ&#2503;ক&#2503; শ&#2497;র&#2497; হব&#2503;
                                loadStream(url, 0);

                                video.muted = false;
                                muteBtn.textContent = "🔊";
                                window.scrollTo({
                                    top: 0,
                                    behavior: "smooth"
                                });
                            }

                            function updateQualityMenu() {
                                qualityMenu.innerHTML = "";
                                if (!hls) return;
                                const levels = hls.levels;
                                levels.forEach((level, i) => {
                                    const opt = document.createElement("option");
                                    opt.value = i;
                                    opt.text = `${level.height}p`;
                                    qualityMenu.appendChild(opt);
                                });
                                const auto = document.createElement("option");
                                auto.value = "auto";
                                auto.text = "Auto";
                                qualityMenu.appendChild(auto);
                                qualityMenu.value = "auto";

                                qualityMenu.onchange = () => {
                                    hls.currentLevel = qualityMenu.value === "auto" ? -1 : parseInt(qualityMenu.value);
                                };
                            }

                            function cycleZoom() {
                                zoomIndex = (zoomIndex + 1) % zoomModes.length;
                                video.style.objectFit = zoomModes[zoomIndex];
                            }

                            function toggleFullscreen() {
                                if (!document.fullscreenElement) video.requestFullscreen();
                                else document.exitFullscreen();
                            }

                            function togglePiP() {
                                if (document.pictureInPictureElement) document.exitPictureInPicture();
                                else video.requestPictureInPicture().catch(() => {});
                            }

                            function toggleMute() {
                                video.muted = !video.muted;
                                muteBtn.textContent = video.muted ? "🔇" : "🔊";
                            }

                            function filterCategory(cat, event) {
                                document.querySelectorAll('.category-bar button').forEach(btn => btn.classList.remove('active'));
                                event.target.classList.add('active');
                                document.querySelectorAll('.channel').forEach(el => {
                                    el.style.display = (cat === el.dataset.category) ? 'block' : 'none';
                                });
                            }

                            function toggleDarkMode() {
                                const root = document.documentElement;
                                const dark = getComputedStyle(root).getPropertyValue('--bg-color') === '#000';
                                root.style.setProperty('--bg-color', dark ? '#f0f0f0' : '#000');
                                root.style.setProperty('--text-color', dark ? '#000' : '#fff');
                            }

                            function loadChannels() {
                                channelGrid.innerHTML = "";
                                channels.forEach(ch => {
                                    const div = document.createElement("div");
                                    div.className = "channel";
                                    div.dataset.category = ch.category;
                                    div.innerHTML = `<img src="${ch.img}" alt="${ch.name}"><p>${ch.name}</p>`;
                                    div.onclick = () => switchChannel(ch.url);
                                    channelGrid.appendChild(div);
                                });
                                filterCategory('BANGLA', {
                                    target: document.querySelector('button[onclick*="BANGLA"]')
                                });
                            }

                            // প&#2509;রত&#2495; ৫ স&#2503;ক&#2503;ন&#2509;ড&#2503; পজ&#2495;শন ল&#2507;ক&#2494;লস&#2509;ট&#2507;র&#2503;জ&#2503; স&#2503;ভ কর&#2494;
                            setInterval(() => {
                                if (!video.paused && !video.ended) {
                                    localStorage.setItem(POSITION_KEY, video.currentTime);
                                }
                            }, 5000);

                            // ন&#2503;টওয়&#2494;র&#2509;ক অন হল&#2503; আগ&#2503;র পজ&#2495;শন থ&#2503;ক&#2503; ভ&#2495;ড&#2495;ও প&#2497;নর&#2494;য় চ&#2494;ল&#2494;ন&#2507;
                            window.addEventListener('online', () => {
                                console.log("Back online, resuming stream...");
                                const lastPosition = parseFloat(localStorage.getItem(POSITION_KEY)) || 0;
                                if (currentChannelUrl) {
                                    loadingOverlay.style.display = "flex";
                                    loadingOverlay.innerText = "&#9203; Resuming Channel...";
                                    loadStream(currentChannelUrl, lastPosition);
                                }
                            });

                            // ন&#2503;টওয়&#2494;র&#2509;ক অফ হল&#2503; ভ&#2495;ড&#2495;ও পজ কর&#2494;
                            window.addEventListener('offline', () => {
                                console.log("Offline, stream paused");
                                loadingOverlay.style.display = "flex";
                                loadingOverlay.innerText = "&#9888;&#65039; Network disconnected";
                                video.pause();
                            });
                            let wakeLock = null;

                            // Wake Lock ন&#2503;ওয&#2492;&#2494;র ফ&#2494;&#2434;শন
                            async function requestWakeLock() {
                                try {
                                    if ('wakeLock' in navigator) {
                                        wakeLock = await navigator.wakeLock.request('screen');
                                        console.log("&#9989; Wake Lock active");
                                        wakeLock.addEventListener('release', () => {
                                            console.log("🔄 Wake Lock released");
                                        });
                                    }
                                } catch (err) {
                                    console.error("&#10060; Wake Lock error:", err);
                                }
                            }

                            // ভ&#2495;ড&#2495;ও play হল&#2503; call করব&#2503;
                            video.addEventListener('play', () => {
                                requestWakeLock();
                            });

                            // প&#2509;রত&#2495; ৩০ স&#2503;ক&#2503;ন&#2509;ড&#2503; চ&#2503;ক করব&#2503; Wake Lock আছ&#2503; ক&#2495;ন&#2494;
                            setInterval(() => {
                                if (document.visibilityState === 'visible' && !wakeLock) {
                                    requestWakeLock();
                                }
                            }, 30000);

                            // শ&#2497;র&#2497;ত&#2503; ল&#2507;ড কর&#2494;
                            loadChannels();
                        </script>





                      




                        <style>
                            #datetime {
                                font-size: 22px;
                                font-weight: bold;
                                color: red;
                                padding: 10px;
                            }
                        </style>



                        <div id="datetime"></div>

                        <script>
                            function updateDateTime() {
                                const now = new Date();

                                const day = now.getDate().toString().padStart(2, '0');
                                const month = (now.getMonth() + 1).toString().padStart(2, '0');
                                const year = now.getFullYear();

                                let hours = now.getHours();
                                const minutes = now.getMinutes().toString().padStart(2, '0');
                                const seconds = now.getSeconds().toString().padStart(2, '0');

                                const ampm = hours >= 12 ? 'PM' : 'AM';
                                hours = hours % 12;
                                hours = hours ? hours : 12; // 0 হল&#2503; 12 ব&#2494;ন&#2494;ন&#2507;
                                const hoursStr = hours.toString().padStart(2, '0');

                                const formattedDateTime = `${day}/${month}/${year} ${hoursStr}:${minutes}:${seconds} ${ampm}`;
                                document.getElementById("datetime").textContent = formattedDateTime;
                            }

                            setInterval(updateDateTime, 1000);
                            updateDateTime(); // প&#2509;রথমব&#2494;র কল
                        </script>






                        <div class="play-button" style="align-items: center; background: none 0% 0% / auto repeat scroll padding-box border-box rgb(229, 9, 20); border-radius: 50%; box-shadow: rgba(229, 9, 20, 0.5) 0px 4px 12px; box-sizing: border-box; color: white; display: flex; height: 60px; justify-content: center; left: 94.6289px; opacity: 0; position: absolute; top: 52.4023px; transform: translate(-50%, -50%) scale(0.8); transition: 0.3s; width: 60px;"><span class="fas fa-play" style="-webkit-font-smoothing: antialiased; box-sizing: border-box; display: inline-block; font-family: &quot;Font Awesome 6 Free&quot;; font-size: 1.5rem; font-variant-alternates: normal; font-variant-east-asian: normal; font-variant-emoji: normal; font-variant-numeric: normal; font-variant-position: normal; font-weight: 900; line-height: 1; margin-left: 4px; text-rendering: auto;"></span></div>
                        <div
                            class="site-footer py-4" style="background-attachment: initial; background-clip: initial; background-image: linear-gradient(to right, rgb(26, 26, 26), rgb(34, 34, 34), rgb(26, 26, 26)); background-origin: initial; background-position: initial; background-repeat: initial; background-size: initial; border-image: linear-gradient(to right, rgb(13, 110, 253), rgb(229, 9, 20), rgb(13, 110, 253)) 1 / 1 / 0 stretch; border-top: 3px solid; box-sizing: border-box; color: white; font-family: &quot;Segoe UI&quot;, Tahoma, Geneva, Verdana, sans-serif; font-size: 16px; margin-top: 50px; padding: 30px 0px 20px; position: relative; text-align: center;">
                            <div class="container" style="--bs-gutter-x: 1.5rem; --bs-gutter-y: 0; box-sizing: border-box; margin-left: auto; margin-right: auto; padding-left: 12px; padding-right: 12px; width: 380px;">
                                <div class="row" style="--bs-gutter-x: 1.5rem; --bs-gutter-y: 0; box-sizing: border-box; display: flex; flex-wrap: wrap; margin-left: -12px; margin-right: -12px; margin-top: 0px;">
                                    <div class="col-md-4" style="box-sizing: border-box; flex-shrink: 0; margin-top: 0px; max-width: 100%; padding-left: 12px; padding-right: 12px; width: 320px;">
                                        <p style="box-sizing: border-box; margin-bottom: 1rem; margin-top: 0px;">
                                            <p style="color: #c108ce;"> 𝙄𝙛 𝙔𝙤𝙪 𝘼𝙧𝙚 𝙁𝙖𝙘𝙞𝙣𝙜 𝘼𝙣𝙮 𝙎𝙩𝙧𝙚𝙖𝙢𝙞𝙣𝙜 𝙞𝙨𝙨𝙪𝙚𝙨, 𝙋𝙡𝙚𝙖𝙨𝙚 𝘾𝙤𝙣𝙩𝙖𝙘𝙩 BountyTab:</p>&nbsp;</p>
                                        <p style="box-sizing: border-box; margin-bottom: 1rem; margin-top: 0px;">
                                            <p style="color: Yellow;"> </p>
                                        </p><a class="btn btn-primary contact-support-btn" href="https://t.me/addlist/-5yBVbjUkR0xYTg1" style="--bs-btn-active-bg: #0a58ca; --bs-btn-active-border-color: #0a53be; --bs-btn-active-color: #fff; --bs-btn-active-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125); --bs-btn-bg: #0d6efd; --bs-btn-border-color: #0d6efd; --bs-btn-border-radius: 0.375rem; --bs-btn-border-width: 1px; --bs-btn-box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.15),0 1px 1px rgba(0, 0, 0, 0.075); --bs-btn-color: #fff; --bs-btn-disabled-bg: #0d6efd; --bs-btn-disabled-border-color: #0d6efd; --bs-btn-disabled-color: #fff; --bs-btn-disabled-opacity: 0.65; --bs-btn-focus-box-shadow: 0 0 0 0.25rem rgba(49,132,253, .5); --bs-btn-focus-shadow-rgb: 49,132,253; --bs-btn-font-size: 1rem; --bs-btn-font-weight: 400; --bs-btn-hover-bg: #0b5ed7; --bs-btn-hover-border-color: red; --bs-btn-hover-color: #fff; --bs-btn-line-height: 1.5; --bs-btn-padding-x: 0.75rem; --bs-btn-padding-y: 0.375rem; background-attachment: initial; background-clip: initial; background-image: linear-gradient(to right, rgb(13, 110, 253), rgb(10, 88, 202)); background-origin: initial; background-position: initial; background-repeat: initial; background-size: initial; border-radius: 50px; border: none; box-shadow: rgba(13, 110, 253, 0.3) 0px 4px 10px; box-sizing: border-box; color: white; cursor: pointer; display: inline-block; line-height: 1.5; padding: 10px 20px; text-decoration-line: none; transition: 0.3s; user-select: none; vertical-align: middle;"><span class="fas fa-headset me-2" style="-webkit-font-smoothing: antialiased; box-sizing: border-box; display: inline-block; font-family: &quot;Font Awesome 6 Free&quot;; font-variant-alternates: normal; font-variant-east-asian: normal; font-variant-emoji: normal; font-variant-numeric: normal; font-variant-position: normal; font-weight: 900; line-height: 1; margin-right: 0.5rem; text-rendering: auto;"></span> 𝘾𝙤𝙣𝙩𝙖𝙘𝙩 𝙊𝙪𝙧 𝙊𝙛𝙛𝙞𝙘𝙞𝙖𝙡 𝙏𝙚𝙖𝙢 🧑&#8205;💻</a></div>
                                </div><br style="box-sizing: border-box;" />
                                <div class="row" style="--bs-gutter-x: 1.5rem; --bs-gutter-y: 0; box-sizing: border-box; display: flex; flex-wrap: wrap; margin-left: -12px; margin-right: -12px; margin-top: 0px;">
                                    <div class="col-md-6" style="box-sizing: border-box; flex-shrink: 0; margin-top: 0px; max-width: 100%; padding-left: 12px; padding-right: 12px; width: 450px;">
                                        <p class="copyright-text mb-0" style="box-sizing: border-box; color: rgba(255, 255, 255, 0.7); font-size: 0.9rem; margin-bottom: 15px; margin-top: 0px;">
                                            <p style="color: blue;">💥 𝘼𝙡𝙡 𝙧𝙞𝙜𝙝𝙩𝙨 𝙍𝙚𝙨𝙚𝙧𝙫𝙚𝙙 𝙏𝙤 BountyTab 🖥&#65039; &#8206; &#8206; &#8206; &#8206; &#8206; &#8206; &#8206; &#8206; &#8206; &#8206; &#8206; &#8206; &#8206; &#8206; &#8206; &#8206;
                                                </p>
                                        </p>
                                    </div>
                                </div>
                            </div>
                    </div>
                    
                </div>
            </div>
        </div>
    </div>
    <!-- Hero Wrapper -->
    <div id='hero-wrapper'>
        <div class='hero-section container row-x1 section' id='hero-section' name='Hero Section'>
            <div class='widget HTML' data-version='2' id='HTML4'>
                <div class='widget-content'>
                    <style>
                        #custom-modal {
                            display: none;
                            position: fixed;
                            z-index: 9999;
                            left: 0;
                            top: 0;
                            width: 100%;
                            height: 100%;
                            background: rgba(0, 0, 0, 0.7);
                            justify-content: center;
                            align-items: center;
                            font-family: Arial, sans-serif;
                        }

                        #custom-modal-content {
                            background: #1e1f26;
                            color: #fff;
                            padding: 30px 20px;
                            border-radius: 12px;
                            max-width: 400px;
                            width: 90%;
                            text-align: center;
                            position: relative;
                            box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
                        }

                        #custom-modal h2 {
                            margin-top: 0;
                            font-size: 22px;
                        }

                        #custom-modal p {
                            font-size: 16px;
                            margin: 15px 0 25px;
                            color: #ddd;
                            line-height: 1.5;
                        }

                        #custom-modal .close {
                            position: absolute;
                            top: 12px;
                            right: 15px;
                            font-size: 24px;
                            cursor: pointer;
                            color: #aaa;
                        }

                        #custom-modal .button-main {
                            display: flex;
                            align-items: center;
                            justify-content: center;
                            background: #0088cc;
                            color: #fff;
                            padding: 15px;
                            border-radius: 6px;
                            text-decoration: none;
                            font-weight: bold;
                            margin-bottom: 12px;
                            font-size: 18px;
                            transition: background 0.3s;
                        }

                        #custom-modal .button-main:hover {
                            background: #007ab3;
                        }

                        #custom-modal .button-main img {
                            width: 24px;
                            height: 24px;
                            margin-right: 10px;
                        }

                        #custom-modal .maybe {
                            display: inline-block;
                            background: #008000;
                            color: #fff;
                            padding: 10px 20px;
                            border-radius: 5px;
                            font-size: 16px;
                            cursor: pointer;
                            text-decoration: none;
                            font-weight: 500;
                            transition: background 0.3s;
                        }

                        #custom-modal .maybe:hover {
                            background: #008000;
                        }
                    </style>

                    <div id="custom-modal">
                        <div id="custom-modal-content">
                            <span class="close">&times;</span>
                            <h2>Join Our Community!</h2>
                            <p>For match links and the latest TV Channels updates, join our Telegram channel. Click below to join!</p>
                            <a href="https://t.me/addlist/-5yBVbjUkR0xYTg1" target="_blank" class="button-main">
      <img src="https://upload.wikimedia.org/wikipedia/commons/8/82/Telegram_logo.svg" alt="Telegram Logo" />
      Join our Official Group 
    </a>
                            <span class="maybe">Close &#10060;</span>
                        </div>
                    </div>

                    <script>
                        // কত স&#2503;ক&#2503;ন&#2509;ড পর&#2503; popup আসব&#2503;
                        var modalDelay = 2000;

                        window.onload = function() {
                            setTimeout(function() {
                                document.getElementById('custom-modal').style.display = 'flex';
                            }, modalDelay);
                        };

                        // Close button
                        document.querySelector('#custom-modal .close').onclick = function() {
                            document.getElementById('custom-modal').style.display = 'none';
                        };

                        // Maybe Later button
                        document.querySelector('#custom-modal .maybe').onclick = function() {
                            document.getElementById('custom-modal').style.display = 'none';
                        };
                    </script>
                </div>
            </div>
        </div>
    </div>
    <!-- Content Wrapper -->
    <div id='content-wrapper'>
        <div class='container row-x1'>
            <!-- Main Wrapper -->
            <main id='main-wrapper'>
                <div class='main section' id='main' name='Main Posts'>
                    <!--Failed to render gadget 'Blog1'.

There was an error processing the markup.
-->
                </div>
            </main>
        </div>
    </div>
    <!-- Footer Wrapper -->
    <footer class='compact-footer' id='footer-wrapper'>
        <div class='container row-x1'>
            <div class='footer-widgets-wrap'>
                <div class='footer freebify-free-widget-ready no-items section' id='footer1' name='Footer 1'></div>
                <div class='footer freebify-free-widget-ready no-items section' id='footer2' name='Footer 2'></div>
                <div class='footer freebify-free-widget-ready no-items section' id='footer3' name='Footer 3'></div>
            </div>
        </div>
        <div id='footer-tag'>
            <div class='key no-items section' id='key' name='Footer 1'></div>
        </div>
    </footer>
    </div>
    <!-- Hosted Plugins -->
    <script src='https://cdnjs.cloudflare.com/ajax/libs/jquery/2.2.4/jquery.min.js'></script>
    <!-- Local Plugins -->
    <script type='text/javascript'>
        //<![CDATA[
        /*! Custom - Theia Sticky Sidebar | v1.7.0 - https://github.com/WeCodePixels/theia-sticky-sidebar */
        ! function(i) {
            i.fn.theiaStickySidebarIfy = function(t) {
                function e(t, e) {
                    var a = o(t, e);
                    a || (console.log("TSS: Body width smaller than options.minWidth. Init is delayed."), i(document).on("scroll." + t.namespace, function(t, e) {
                        return function(a) {
                            var n = o(t, e);
                            n && i(this).unbind(a)
                        }
                    }(t, e)), i(window).on("resize." + t.namespace, function(t, e) {
                        return function(a) {
                            var n = o(t, e);
                            n && i(this).unbind(a)
                        }
                    }(t, e)))
                }

                function o(t, e) {
                    return t.initialized === !0 || !(i("body").width() < t.minWidth) && (a(t, e), !0)
                }

                function a(t, e) {
                    t.initialized = !0;
                    e.each(function() {
                        function e() {
                            a.fixedScrollTop = 0, a.sidebar.css({
                                "min-height": "1px"
                            }), a.stickySidebar.css({
                                position: "static",
                                width: "",
                                transform: "none"
                            })
                        }

                        function o(t) {
                            var e = t.height();
                            return t.children().each(function() {
                                e = Math.max(e, i(this).height())
                            }), e
                        }
                        var a = {};
                        if (a.sidebar = i(this), a.options = t || {}, a.container = i(a.options.containerSelector), 0 == a.container.length && (a.container = a.sidebar.parent()), a.sidebar.parent().css("-webkit-transform", "none"), a.sidebar.css({
                                position: a.options.defaultPosition,
                                overflow: "visible",
                                "-webkit-box-sizing": "border-box",
                                "-moz-box-sizing": "border-box",
                                "box-sizing": "border-box"
                            }), a.stickySidebar = a.sidebar.find(".theiaStickySidebarIfy"), 0 == a.stickySidebar.length) {
                            var s = /(?:text|application)\/(?:x-)?(?:javascript|ecmascript)/i;
                            a.sidebar.find("script").filter(function(i, t) {
                                return 0 === t.type.length || t.type.match(s)
                            }).remove(), a.stickySidebar = i("<div>").addClass("theiaStickySidebarIfy").append(a.sidebar.children()), a.sidebar.append(a.stickySidebar)
                        }
                        a.marginBottom = parseInt(a.sidebar.css("margin-bottom")), a.paddingTop = parseInt(a.sidebar.css("padding-top")), a.paddingBottom = parseInt(a.sidebar.css("padding-bottom"));
                        var r = a.stickySidebar.offset().top,
                            d = a.stickySidebar.outerHeight();
                        a.stickySidebar.css("padding-top", 1), a.stickySidebar.css("padding-bottom", 1), r -= a.stickySidebar.offset().top, d = a.stickySidebar.outerHeight() - d - r, 0 == r ? (a.stickySidebar.css("padding-top", 0), a.stickySidebarPaddingTop = 0) : a.stickySidebarPaddingTop = 1, 0 == d ? (a.stickySidebar.css("padding-bottom", 0), a.stickySidebarPaddingBottom = 0) : a.stickySidebarPaddingBottom = 1, a.previousScrollTop = null, a.fixedScrollTop = 0, e(), a.onScroll = function(a) {
                            if (a.stickySidebar.is(":visible")) {
                                if (i("body").width() < a.options.minWidth) return void e();
                                if (a.options.disableOnResponsiveLayouts) {
                                    var s = a.sidebar.outerWidth("none" == a.sidebar.css("float"));
                                    if (s + 50 > a.container.width()) return void e()
                                }
                                var r = i(document).scrollTop(),
                                    d = "static";
                                if (r >= a.sidebar.offset().top + (a.paddingTop - a.options.additionalMarginTop)) {
                                    var c, p = a.paddingTop + t.additionalMarginTop,
                                        b = a.paddingBottom + a.marginBottom + t.additionalMarginBottom,
                                        l = a.sidebar.offset().top,
                                        f = a.sidebar.offset().top + o(a.container),
                                        h = 0 + t.additionalMarginTop,
                                        g = a.stickySidebar.outerHeight() + p + b < i(window).height();
                                    c = g ? h + a.stickySidebar.outerHeight() : i(window).height() - a.marginBottom - a.paddingBottom - t.additionalMarginBottom;
                                    var u = l - r + a.paddingTop,
                                        S = f - r - a.paddingBottom - a.marginBottom,
                                        y = a.stickySidebar.offset().top - r,
                                        m = a.previousScrollTop - r;
                                    "fixed" == a.stickySidebar.css("position") && "modern" == a.options.sidebarBehavior && (y += m), "stick-to-top" == a.options.sidebarBehavior && (y = t.additionalMarginTop), "stick-to-bottom" == a.options.sidebarBehavior && (y = c - a.stickySidebar.outerHeight()), y = m > 0 ? Math.min(y, h) : Math.max(y, c - a.stickySidebar.outerHeight()), y = Math.max(y, u), y = Math.min(y, S - a.stickySidebar.outerHeight());
                                    var k = a.container.height() == a.stickySidebar.outerHeight();
                                    d = (k || y != h) && (k || y != c - a.stickySidebar.outerHeight()) ? r + y - a.sidebar.offset().top - a.paddingTop <= t.additionalMarginTop ? "static" : "absolute" : "fixed"
                                }
                                if ("fixed" == d) {
                                    var v = i(document).scrollLeft();
                                    a.stickySidebar.css({
                                        position: "fixed",
                                        width: n(a.stickySidebar) + "px",
                                        transform: "none",
                                        top: y + "px"
                                    })
                                } else if ("absolute" == d) {
                                    var x = {};
                                    "absolute" != a.stickySidebar.css("position") && (x.position = "absolute", x.transform = "none", x.top = (r + y - a.sidebar.offset().top - a.stickySidebarPaddingTop - a.stickySidebarPaddingBottom) + "px"), x.width = n(a.stickySidebar) + "px", a.stickySidebar.css(x)
                                } else "static" == d && e();
                                "static" != d && 1 == a.options.updateSidebarHeight && a.sidebar.css({
                                    "min-height": a.stickySidebar.outerHeight() + a.stickySidebar.offset().top - a.sidebar.offset().top + a.paddingBottom
                                }), a.previousScrollTop = r
                            }
                        }, a.onScroll(a), i(document).on("scroll." + a.options.namespace, function(i) {
                            return function() {
                                i.onScroll(i)
                            }
                        }(a)), i(window).on("resize." + a.options.namespace, function(i) {
                            return function() {
                                i.stickySidebar.css({
                                    position: "static"
                                }), i.onScroll(i)
                            }
                        }(a)), "undefined" != typeof ResizeSensor && new ResizeSensor(a.stickySidebar[0], function(i) {
                            return function() {
                                i.onScroll(i)
                            }
                        }(a))
                    })
                }

                function n(i) {
                    var t;
                    try {
                        t = i[0].getBoundingClientRect().width
                    } catch (i) {}
                    return "undefined" == typeof t && (t = i.width()), t
                }
                var s = {
                    containerSelector: "",
                    additionalMarginTop: 0,
                    additionalMarginBottom: 0,
                    updateSidebarHeight: !0,
                    minWidth: 0,
                    disableOnResponsiveLayouts: !0,
                    sidebarBehavior: "modern",
                    defaultPosition: "relative",
                    namespace: "TSS"
                };
                return t = i.extend(s, t), t.additionalMarginTop = parseInt(t.additionalMarginTop) || 0, t.additionalMarginBottom = parseInt(t.additionalMarginBottom) || 0, e(t, this), this
            }
        }(jQuery);


        /*! MenuIfy by Templateify | v1.0.0 - https://www.templateify.com */
        ! function(a) {
            a.fn.menuify = function() {
                return this.each(function() {
                    var $t = a(this),
                        b = $t.find('.LinkList ul > li').children('a'),
                        c = b.length;
                    for (var i = 0; i < c; i++) {
                        var d = b.eq(i),
                            h = d.text();
                        if (h.charAt(0) !== '_') {
                            var e = b.eq(i + 1),
                                j = e.text();
                            if (j.charAt(0) === '_') {
                                var m = d.parent();
                                m.append('<ul class="sub-menu m-sub"/>');
                            }
                        }
                        if (h.charAt(0) === '_') {
                            d.text(h.replace('_', ''));
                            d.parent().appendTo(m.children('.sub-menu'));
                        }
                    }
                    for (var i = 0; i < c; i++) {
                        var f = b.eq(i),
                            k = f.text();
                        if (k.charAt(0) !== '_') {
                            var g = b.eq(i + 1),
                                l = g.text();
                            if (l.charAt(0) === '_') {
                                var n = f.parent();
                                n.append('<ul class="sub-menu2 m-sub"/>');
                            }
                        }
                        if (k.charAt(0) === '_') {
                            f.text(k.replace('_', ''));
                            f.parent().appendTo(n.children('.sub-menu2'));
                        }
                    }
                    $t.find('.LinkList ul li ul').parent('li').addClass('has-sub');
                });
            }
        }(jQuery);

        /*! Tabify by Templateify | v1.0.0 - https://www.templateify.com */
        ! function(a) {
            a.fn.tabify = function(b) {
                b = jQuery.extend({
                    onHover: false,
                    animated: true,
                    transition: 'fadeInUp'
                }, b);
                return this.each(function() {
                    var e = a(this),
                        c = e.children('[tab-ify]'),
                        d = 0,
                        n = 'tab-animated',
                        k = 'tab-active';
                    if (b.onHover == true) {
                        var event = 'mouseenter'
                    } else {
                        var event = 'click'
                    }
                    e.prepend('<ul class="select-tab"></ul>');
                    c.each(function() {
                        if (b.animated == true) {
                            a(this).addClass(n)
                        }
                        e.find('.select-tab').append('<li><a href="javascript:;">' + a(this).attr('tab-ify') + '</a></li>')
                    }).eq(d).addClass(k).addClass('tab-' + b.transition);
                    e.find('.select-tab a').on(event, function() {
                        var f = a(this).parent().index();
                        a(this).closest('.select-tab').find('.active').removeClass('active');
                        a(this).parent().addClass('active');
                        c.removeClass(k).removeClass('tab-' + b.transition).eq(f).addClass(k).addClass('tab-' + b.transition);
                        return false
                    }).eq(d).parent().addClass('active')
                })
            }
        }(jQuery);

        /*! ResizeIfy - LazyIfy on Scroll by Templateify | v1.2.0 - https://www.templateify.com */
        ! function(a) {
            a.fn.lazyify = function() {
                return this.each(function() {
                    var t = a(this),
                        dImg = t.attr('data-image'),
                        iWid = Math.round(t.width()),
                        iHei = Math.round(t.height()),
                        iSiz = 'w' + iWid + '-h' + iHei + '-p-k-no-nu',
                        img = '';
                    if (dImg.match('/s72-c')) {
                        img = dImg.replace('/s72-c', '/' + iSiz);
                    } else if (dImg.match('/w72-h')) {
                        img = dImg.replace('/w72-h72-p-k-no-nu', '/' + iSiz);
                    } else if (dImg.match('=w72-h')) {
                        img = dImg.replace('=w72-h72-p-k-no-nu', '=' + iSiz);
                    } else {
                        img = dImg;
                    }
                    a(window).on('load resize scroll', lazyOnScroll);

                    function lazyOnScroll() {
                        var wHeight = a(window).height(),
                            scrTop = a(window).scrollTop(),
                            offTop = t.offset().top;
                        if (scrTop + wHeight > offTop) {
                            var n = new Image();
                            n.onload = function() {
                                t.attr('style', 'background-image:url(' + this.src + ')').addClass('lazy-ify');
                            }, n.src = img;
                        }
                    }
                    lazyOnScroll();
                });
            }
        }(jQuery);

        /*! jQuery replaceText by "Cowboy" Ben Alman | v1.1.0 - http://benalman.com/projects/jquery-replacetext-plugin/ */
        (function($) {
            $.fn.replaceText = function(b, a, c) {
                return this.each(function() {
                    var f = this.firstChild,
                        g, e, d = [];
                    if (f) {
                        do {
                            if (f.nodeType === 3) {
                                g = f.nodeValue;
                                e = g.replace(b, a);
                                if (e !== g) {
                                    if (!c && /</.test(e)) {
                                        $(f).before(e);
                                        d.push(f)
                                    } else {
                                        f.nodeValue = e
                                    }
                                }
                            }
                        } while (f = f.nextSibling)
                    }
                    d.length && $(d).remove()
                })
            }
        })(jQuery);




        //]]>
    </script>
    <!-- Theme Scripts -->
    <script>
        //<![CDATA[
        function shortCodeIfy(_0xeb1cxf, _0xeb1cx10, _0xeb1cx11) {
            var _0xeb1cx12 = _0xeb1cxf.split("$");
            for (var _0xeb1cx14 = 0; _0xeb1cx14 < _0xeb1cx12.length; _0xeb1cx14++) {
                var _0xeb1cx15 = _0xeb1cx12[_0xeb1cx14].split("=");
                if (_0xeb1cx15[0].trim() == _0xeb1cx10) {
                    return null != (_0xeb1cx11 = _0xeb1cx15[1]).match(/[^{\}]+(?=})/g) && String(_0xeb1cx11.match(/[^{\}]+(?=})/g)).trim();
                }
            };
            return false;
        }

        function msgError() {
            return "<span class=\"error-msg\"><b>Error:</b> No Results Found</span>";
        }

        function beforeLoader() {
            return "<div class=\"loader\"/>";
        }

        function getFeedUrl(_0xeb1cxf, _0xeb1cx10, _0xeb1cx11) {
            var _0xeb1cx12 = "";
            switch (_0xeb1cx11) {
                case "recent":
                    _0xeb1cx12 = "/feeds/posts/default?alt=json&max-results=" + _0xeb1cx10;
                    break;
                case "comments":
                    _0xeb1cx12 = "list1" == _0xeb1cxf ? "/feeds/comments/default?alt=json&max-results=" + _0xeb1cx10 : "/feeds/posts/default/-/" + _0xeb1cx11 + "?alt=json&max-results=" + _0xeb1cx10;
                    break;
                default:
                    _0xeb1cx12 = "/feeds/posts/default/-/" + _0xeb1cx11 + "?alt=json&max-results=" + _0xeb1cx10;
            };
            return _0xeb1cx12;
        }

        function getPostLink(_0xeb1cxf, _0xeb1cx10) {
            for (var _0xeb1cx11 = 0; _0xeb1cx11 < _0xeb1cxf[_0xeb1cx10].link.length; _0xeb1cx11++) {
                if ("alternate" == _0xeb1cxf[_0xeb1cx10].link[_0xeb1cx11].rel) {
                    var _0xeb1cx12 = _0xeb1cxf[_0xeb1cx10].link[_0xeb1cx11].href;
                    break;
                }
            };
            return _0xeb1cx12;
        }

        function getPostTitle(_0xeb1cxf, _0xeb1cx10) {
            if (_0xeb1cxf[_0xeb1cx10].title.$t) {
                var _0xeb1cx11 = _0xeb1cxf[_0xeb1cx10].title.$t;
            } else {
                _0xeb1cx11 = messages.noTitle;
            };
            return _0xeb1cx11;
        }

        function getFirstImage(_0xeb1cxf, _0xeb1cx10) {
            var _0xeb1cx11 = $("<div>").html(_0xeb1cxf).find("img:first").attr("src");
            var _0xeb1cx12 = _0xeb1cx11.lastIndexOf("/") || 0;
            var _0xeb1cx13 = _0xeb1cx11.lastIndexOf("/", _0xeb1cx12 - 1) || 0;
            var _0xeb1cx14 = _0xeb1cx11.substring(0, _0xeb1cx13);
            var _0xeb1cx15 = _0xeb1cx11.substring(_0xeb1cx13, _0xeb1cx12);
            var _0xeb1cx1c = _0xeb1cx11.substring(_0xeb1cx12);
            if (_0xeb1cx15.match(/\/s[0-9]+/g) || _0xeb1cx15.match(/\/w[0-9]+/g) || "/d" == _0xeb1cx15) {
                _0xeb1cx15 = "/w72-h72-p-k-no-nu";
            }
            return _0xeb1cx14 + _0xeb1cx15 + _0xeb1cx1c;
        }

        function getPostImage(_0xeb1cxf, _0xeb1cx10, _0xeb1cx11) {
            var _0xeb1cx12 = _0xeb1cxf[_0xeb1cx10].content.$t;
            if (_0xeb1cxf[_0xeb1cx10].media$thumbnail) {
                var _0xeb1cx13 = _0xeb1cxf[_0xeb1cx10].media$thumbnail.url;
            } else {
                _0xeb1cx13 = "https://4.bp.blogspot.com/-eALXtf-Ljts/WrQYAbzcPUI/AAAAAAAABjY/vptx-N2H46oFbiCqbSe2JgVSlHhyl0MwQCK4BGAYYCw/s72-c/nth-ify.png";
            };
            return _0xeb1cx12.indexOf(_0xeb1cx12.match(/<iframe(?:.+)?src=(?:.+)?(?:www.youtube.com)/g)) > -1 ? _0xeb1cx12.indexOf("<img") > -1 ? _0xeb1cx12.indexOf(_0xeb1cx12.match(/<iframe(?:.+)?src=(?:.+)?(?:www.youtube.com)/g)) < _0xeb1cx12.indexOf("<img") ? _0xeb1cx13.replace("/default.", "/maxresdefault.") : getFirstImage(_0xeb1cx12) : _0xeb1cx13.replace("/default.", "/maxresdefault.") : _0xeb1cx12.indexOf("<img") > -1 ? getFirstImage(_0xeb1cx12) : "https://4.bp.blogspot.com/-eALXtf-Ljts/WrQYAbzcPUI/AAAAAAAABjY/vptx-N2H46oFbiCqbSe2JgVSlHhyl0MwQCK4BGAYYCw/s72-c/nth-ify.png";
        }

        function getPostLabel(_0xeb1cxf, _0xeb1cx10) {
            if (_0xeb1cxf[_0xeb1cx10].category) {
                var _0xeb1cx11 = "<span class=\"entry-category\">" + _0xeb1cxf[_0xeb1cx10].category[0].term + "</span>";
            } else {
                _0xeb1cx11 = "";
            };
            return _0xeb1cx11;
        }

        function getVideoClass(_0xeb1cxf, _0xeb1cx10) {
            return _0xeb1cxf.match("img.youtube.com") ? "is-video" : "is-image";
        }

        function getAjax(_0xeb1cxf, _0xeb1cx10, _0xeb1cx11, _0xeb1cx12) {
            switch (_0xeb1cx10) {
                case "related":
                    if (0 == _0xeb1cx12) {
                        _0xeb1cx12 = "geterror404";
                    }
                    var _0xeb1cx13 = getFeedUrl(_0xeb1cx10, _0xeb1cx11, _0xeb1cx12);
                    $.ajax({
                        url: _0xeb1cx13,
                        type: "GET",
                        dataType: "json",
                        cache: true,
                        beforeSend: function(_0xeb1cx11) {
                            switch (_0xeb1cx10) {
                                case "related":
                                    _0xeb1cxf.html("<div class=\"loader\"/>").parent().addClass("show-ify");
                            }
                        },
                        success: function(_0xeb1cx11) {
                            var _0xeb1cx12 = "";
                            switch (_0xeb1cx10) {
                                case "related":
                                    _0xeb1cx12 = "<div class=\"related-posts\">";
                            };
                            var _0xeb1cx13 = _0xeb1cx11.feed.entry;
                            if (null != _0xeb1cx13) {
                                for (var _0xeb1cx14 = 0; _0xeb1cx14 < _0xeb1cx13.length; _0xeb1cx14++) {
                                    var _0xeb1cx1c = getPostLink(_0xeb1cx13, _0xeb1cx14);
                                    var _0xeb1cx21 = getPostTitle(_0xeb1cx13, _0xeb1cx14, _0xeb1cx1c);
                                    var _0xeb1cx22 = getPostImage(_0xeb1cx13, _0xeb1cx14, _0xeb1cx1c);
                                    getPostLabel(_0xeb1cx13, _0xeb1cx14);
                                    var _0xeb1cx23 = _0xeb1cx22.match("img.youtube.com") ? "is-video" : "is-image";
                                    var _0xeb1cx24 = "";
                                    switch (_0xeb1cx10) {
                                        case "related":
                                            _0xeb1cx24 += "<article class=\"related-item post item-" + _0xeb1cx14 + "\"><a class=\"entry-image-wrap " + _0xeb1cx23 + "\" href=\"" + _0xeb1cx1c + "\"><span class=\"entry-thumb\" data-image=\"" + _0xeb1cx22 + "\"/></a><div class=\"entry-header\"><h2 class=\"entry-title\"><a href=\"" + _0xeb1cx1c + "\">" + _0xeb1cx21 + "</a></h2></div></article>";
                                    };
                                    _0xeb1cx12 += _0xeb1cx24;
                                }
                            } else {
                                _0xeb1cx12 = "<span class=\"error-msg\"><b>Error:</b> No Results Found</span>";
                            };
                            _0xeb1cx12 += "</div>";
                            _0xeb1cxf.html(_0xeb1cx12);
                            _0xeb1cxf.find("span.entry-thumb").lazyify();
                        },
                        error: function() {
                            _0xeb1cxf.html("<span class=\"error-msg\"><b>Error:</b> No Results Found</span>");
                        }
                    });
            }
        }

        function ajaxRelated(_0xeb1cxf, _0xeb1cx10, _0xeb1cx11, _0xeb1cx12, _0xeb1cx13) {
            if (_0xeb1cx13.match("getrelated")) {
                return getAjax(_0xeb1cxf, _0xeb1cx10, _0xeb1cx11, _0xeb1cx12);
            }
        }

        function beautiAvatar(_0xeb1cxf) {
            $(_0xeb1cxf).attr("src", function(_0xeb1cxf, _0xeb1cx10) {
                return _0xeb1cx10 = (_0xeb1cx10 = _0xeb1cx10.replace("//resources.blogblog.com/img/blank.gif", "//4.bp.blogspot.com/-oSjP8F09qxo/Wy1J9dp7b0I/AAAAAAAACF0/ggcRfLCFQ9s2SSaeL9BFSE2wyTYzQaTyQCK4BGAYYCw/s35-r/avatar.jpg")).replace("//img1.blogblog.com/img/blank.gif", "//4.bp.blogspot.com/-oSjP8F09qxo/Wy1J9dp7b0I/AAAAAAAACF0/ggcRfLCFQ9s2SSaeL9BFSE2wyTYzQaTyQCK4BGAYYCw/s35-r/avatar.jpg");
            });
        }
        $("#freebify-free-main-menu").menuify();
        $("#freebify-free-main-menu .widget").addClass("show-menu");
        $(".search-toggle.show").on("click", function() {
            $("body").addClass("search-active");
            $("#nav-search-wrap").fadeIn(170).find("input").focus();
        });
        $(".search-toggle.hide").on("click", function() {
            $("body").removeClass("search-active");
            $("#nav-search-wrap").fadeOut(170).find("input").blur();
        });
        $(".sidebar .social-icons li a").each(function(_0xeb1cxf) {
            var _0xeb1cx10 = $(this);
            var _0xeb1cx11 = _0xeb1cx10.attr("href").split("$");
            _0xeb1cxf = _0xeb1cx11[0].trim();
            if (null != _0xeb1cx11[1]) {
                _0xeb1cx10.find("span.text").text(_0xeb1cx11[1].trim());
            }
            _0xeb1cx10.attr("href", _0xeb1cxf);
        });
        $(".follow-by-email-text").each(function() {
            var _0xeb1cxf = $(this);
            if ("" != followByEmailText) {
                _0xeb1cxf.text(followByEmailText);
            }
        });
        $(".post-body a").each(function() {
            var _0xeb1cxf = $(this);
            var _0xeb1cx10 = _0xeb1cxf.text().trim();
            var _0xeb1cx11 = _0xeb1cx10.toLowerCase();
            var _0xeb1cx12 = shortCodeIfy(_0xeb1cx10, "text");
            var _0xeb1cx13 = shortCodeIfy(_0xeb1cx10, "size");
            if (_0xeb1cx11.match("getdownload") && 0 != _0xeb1cx12) {
                _0xeb1cxf.wrap("<div class=\"file-btn\"/>");
                _0xeb1cxf.addClass("button download").text(_0xeb1cx12);
                if (0 != _0xeb1cx13) {
                    _0xeb1cxf.parent(".file-btn").append("<span class=\"file-size\">" + _0xeb1cx13 + "</span>");
                }
            }
        });
        $(".post-body a").each(function() {
            var _0xeb1cxf = $(this);
            var _0xeb1cx10 = _0xeb1cxf.text().trim();
            var _0xeb1cx11 = _0xeb1cx10.split("/");
            var _0xeb1cx12 = _0xeb1cx11[0];
            var _0xeb1cx13 = _0xeb1cx11[1];
            var _0xeb1cx14 = _0xeb1cx11.pop();
            if (_0xeb1cx10.match("button")) {
                _0xeb1cxf.addClass("button").text(_0xeb1cx12);
                if ("button" != _0xeb1cx13) {
                    _0xeb1cxf.addClass(_0xeb1cx13);
                }
                if ("button" != _0xeb1cx14) {
                    _0xeb1cxf.addClass("colored-button").css({
                        "background-color": _0xeb1cx14
                    });
                }
            }
        });
        $(".post-body strike").each(function() {
            var _0xeb1cxf = $(this);
            var _0xeb1cx10 = _0xeb1cxf.text().trim();
            var _0xeb1cx11 = _0xeb1cxf.html();
            if (_0xeb1cx10.match("contact-form")) {
                _0xeb1cxf.replaceWith("<div class=\"contact-form\"/>");
                $(".contact-form").append($("#ContactForm1"));
            }
            if (_0xeb1cx10.match("alert-success")) {
                _0xeb1cxf.replaceWith("<div class=\"alert-message alert-success short-b\">" + _0xeb1cx11 + "</div>");
            }
            if (_0xeb1cx10.match("alert-info")) {
                _0xeb1cxf.replaceWith("<div class=\"alert-message alert-info short-b\">" + _0xeb1cx11 + "</div>");
            }
            if (_0xeb1cx10.match("alert-warning")) {
                _0xeb1cxf.replaceWith("<div class=\"alert-message alert-warning short-b\">" + _0xeb1cx11 + "</div>");
            }
            if (_0xeb1cx10.match("alert-error")) {
                _0xeb1cxf.replaceWith("<div class=\"alert-message alert-error short-b\">" + _0xeb1cx11 + "</div>");
            }
            if (_0xeb1cx10.match("left-sidebar")) {
                _0xeb1cxf.replaceWith("<style>.is-single #main-wrapper{float:right}.is-single #sidebar-wrapper{float:left}</style>");
            }
            if (_0xeb1cx10.match("right-sidebar")) {
                _0xeb1cxf.replaceWith("<style>.is-single #main-wrapper{float:left}.is-single #sidebar-wrapper{float:right}</style>");
            }
            if (_0xeb1cx10.match("full-width")) {
                _0xeb1cxf.replaceWith("<style>.is-single #main-wrapper{width:100%}.is-single #sidebar-wrapper{display:none}</style>");
            }
            if (_0xeb1cx10.match("code-box")) {
                _0xeb1cxf.replaceWith("<pre class=\"code-box short-b\">" + _0xeb1cx11 + "</pre>");
            }
            $(".post-body .short-b").find("b").each(function() {
                var _0xeb1cxf = $(this);
                var _0xeb1cx10 = _0xeb1cxf.text().trim();
                if (_0xeb1cx10.match("alert-success") || _0xeb1cx10.match("alert-info") || _0xeb1cx10.match("alert-warning") || _0xeb1cx10.match("alert-error") || _0xeb1cx10.match("code-box")) {
                    _0xeb1cxf.replaceWith("");
                }
            });
        });
        $(".freebify-free-share-links .window-ify").on("click", function() {
            var _0xeb1cxf = $(this);
            var _0xeb1cx10 = _0xeb1cxf.data("url");
            var _0xeb1cx11 = _0xeb1cxf.data("width");
            var _0xeb1cx12 = _0xeb1cxf.data("height");
            var _0xeb1cx13 = window.screen.width;
            var _0xeb1cx14 = window.screen.height;
            var _0xeb1cx15 = Math.round(_0xeb1cx13 / 2 - _0xeb1cx11 / 2);
            var _0xeb1cx1c = Math.round(_0xeb1cx14 / 2 - _0xeb1cx12 / 2);
            window.open(_0xeb1cx10, "_blank", "scrollbars=yes,resizable=yes,toolbar=no,location=yes,width=" + _0xeb1cx11 + ",height=" + _0xeb1cx12 + ",left=" + _0xeb1cx15 + ",top=" + _0xeb1cx1c).focus();
        });
        $(".freebify-free-share-links").each(function() {
            var _0xeb1cxf = $(this);
            _0xeb1cxf.find(".show-hid a").on("click", function() {
                _0xeb1cxf.toggleClass("show-hidden");
            });
        });
        $(".about-author .author-description span a").each(function() {
            var _0xeb1cxf = $(this);
            var _0xeb1cx10 = _0xeb1cxf.text().trim();
            var _0xeb1cx11 = _0xeb1cxf.attr("href");
            _0xeb1cxf.replaceWith("<li class=\"" + _0xeb1cx10 + "\"><a href=\"" + _0xeb1cx11 + "\" title=\"" + _0xeb1cx10 + "\" target=\"_blank\"/></li>");
            $(".description-links").append($(".author-description span li"));
            $(".description-links").addClass("show");
        });
        $(".freebify-free-related-content").each(function() {
            var _0xeb1cxf = $(this);
            var _0xeb1cx10 = _0xeb1cxf.find(".related-tag").attr("data-label");
            ajaxRelated(_0xeb1cxf, "related", relatedPostsNum, _0xeb1cx10, "getrelated");
        });
        $(".freebify-free-blog-post-comments").each(function() {
            var _0xeb1cxf = $(this);
            switch (commentsSystem) {
                case "blogger":
                    ;
                case "disqus":
                    ;
                case "facebook":
                    _0xeb1cxf.addClass("comments-system-blogger").show();
                    $(".entry-meta .entry-comments-link").addClass("show");
                    beautiAvatar(".avatar-image-container img");
                    break;
                case "hide":
                    _0xeb1cxf.hide();
                    break;
                default:
                    _0xeb1cxf.addClass("comments-system-blogger").show();
                    $(".entry-meta .entry-comments-link").addClass("show");
                    beautiAvatar(".avatar-image-container img");
            };
            var _0xeb1cx10 = _0xeb1cxf.find(".comments .comment-reply");
            var _0xeb1cx11 = _0xeb1cxf.find(".comments #top-continue");
            var _0xeb1cx12 = _0xeb1cxf.find("#show-comment-form");
            _0xeb1cx10.on("click", function() {
                _0xeb1cx11.show();
                _0xeb1cxf.addClass("comment-form-visible");
                _0xeb1cx12.remove();
            });
            _0xeb1cx11.on("click", function() {
                _0xeb1cx11.hide();
            });
            _0xeb1cx12.on("click", function() {
                _0xeb1cxf.addClass("comment-form-visible");
                _0xeb1cx12.remove();
            });
        });
        $(function() {
            $(".index-post .entry-image-wrap .entry-thumb, .PopularPosts .entry-image-wrap .entry-thumb, .FeaturedPost .entry-image-wrap .entry-thumb,.about-author .author-avatar").lazyify();
            $("#freebify-free-mobile-menu").each(function() {
                var _0xeb1cxf = $(this);
                var _0xeb1cx10 = $("#freebify-free-main-menu-nav").clone();
                _0xeb1cx10.attr("id", "main-mobile-nav");
                _0xeb1cx10.appendTo(_0xeb1cxf);
                $(".mobile-menu-toggle, .hide-freebify-free-mobile-menu, .overlay").on("click", function() {
                    $("body").toggleClass("nav-active");
                });
                $(".freebify-free-mobile-menu .has-sub").append("<div class=\"submenu-toggle\"/>");
                $(".freebify-free-mobile-menu ul li .submenu-toggle").on("click", function(_0xeb1cxf) {
                    if ($(this).parent().hasClass("has-sub")) {
                        _0xeb1cxf.preventDefault();
                        if ($(this).parent().hasClass("show")) {
                            $(this).parent().removeClass("show").find("> .m-sub").slideToggle(170);
                        } else {
                            $(this).parent().addClass("show").children(".m-sub").slideToggle(170);
                        }
                    }
                });
            });
            $(".mobile-navbar-menu").each(function() {
                var _0xeb1cxf = $(this);
                $("#footer-menu ul.link-list").clone().appendTo(_0xeb1cxf);
            });
            $(".mobile-navbar-social").each(function() {
                var _0xeb1cxf = $(this);
                var _0xeb1cx10 = $("#footer-wrapper ul.social").first().clone();
                _0xeb1cx10.removeClass("social-bg-hover");
                _0xeb1cx10.appendTo(_0xeb1cxf);
            });
            $(".headerify-wrap .headerify").each(function() {
                var _0xeb1cxf = $(this);
                if (1 == fixedMenu && _0xeb1cxf.length > 0) {
                    var _0xeb1cx10 = $(document).scrollTop();
                    var _0xeb1cx11 = _0xeb1cxf.offset().top;
                    var _0xeb1cx12 = _0xeb1cxf.height();
                    var _0xeb1cx13 = _0xeb1cx11 + _0xeb1cx12;
                    $(window).scroll(function() {
                        var _0xeb1cx11 = $(document).scrollTop();
                        if (_0xeb1cx11 < $("#footer-wrapper").offset().top - _0xeb1cx12) {
                            if (_0xeb1cx11 > _0xeb1cx13) {
                                _0xeb1cxf.addClass("is-fixed");
                            } else if (_0xeb1cx11 <= 0) {
                                _0xeb1cxf.removeClass("is-fixed");
                            }
                            if (_0xeb1cx11 > _0xeb1cx10) {
                                _0xeb1cxf.removeClass("show");
                            } else {
                                _0xeb1cxf.addClass("show");
                            }
                            _0xeb1cx10 = $(document).scrollTop();
                        }
                    });
                }
            });
            $(".is-single #main-wrapper, .is-single #sidebar-wrapper").each(function() {
                if (1 == fixedSidebar) {
                    $(this).theiaStickySidebarIfy({
                        containerSelector: "#content-wrapper > .container",
                        additionalMarginTop: 35,
                        additionalMarginBottom: 35
                    });
                }
            });
            $("#post-body iframe").each(function() {
                var _0xeb1cxf = $(this);
                if (_0xeb1cxf.attr("src").match("www.youtube.com")) {
                    _0xeb1cxf.wrap("<div class=\"responsive-video-wrap\"/>");
                }
            });
            $("p.comment-content").each(function() {
                var _0xeb1cxf = $(this);
                _0xeb1cxf.replaceText(/(https:\/\/\S+(\.png|\.jpeg|\.jpg|\.gif))/g, "<img src=\"$1\"/>");
                _0xeb1cxf.replaceText(/(?:https:\/\/)?(?:www\.)?(?:youtube\.com)\/(?:watch\?v=)?(.+)/g, "<div class=\"responsive-video-wrap\"><iframe id=\"youtube\" width=\"100%\" height=\"358\" src=\"https://www.youtube.com/embed/$1\" frameborder=\"0\" allow=\"accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture\" allowfullscreen></iframe></div>");
            });
            $("#freebify-free-load-more-link").each(function() {
                var _0xeb1cxf = $(this).data("load");
                if (_0xeb1cxf) {
                    $("#freebify-free-load-more-link").show();
                }
                $("#freebify-free-load-more-link").on("click", function(_0xeb1cx10) {
                    $("#freebify-free-load-more-link").hide();
                    $.ajax({
                        url: _0xeb1cxf,
                        success: function(_0xeb1cx10) {
                            var _0xeb1cx11 = $(_0xeb1cx10).find(".blog-posts");
                            _0xeb1cx11.find(".index-post").addClass("post-animated post-fadeInUp");
                            $(".blog-posts").append(_0xeb1cx11.html());
                            if (_0xeb1cxf = $(_0xeb1cx10).find("#freebify-free-load-more-link").data("load")) {
                                $("#freebify-free-load-more-link").show();
                            } else {
                                $("#freebify-free-load-more-link").hide();
                                $("#blog-pager .no-more").addClass("show");
                            }
                            $(".index-post .entry-image-wrap .entry-thumb").lazyify();
                        },
                        beforeSend: function() {
                            $("#blog-pager .loading").show();
                        },
                        complete: function() {
                            $("#blog-pager .loading").hide();
                        }
                    });
                    _0xeb1cx10.preventDefault();
                });
            });
            $("#back-top").each(function() {
                var _0xeb1cxf = $(this);
                $(window).on("scroll", function() {
                    if ($(this).scrollTop() >= 100) {
                        _0xeb1cxf.fadeIn(250);
                    } else {
                        _0xeb1cxf.fadeOut(250);
                    }
                    if (_0xeb1cxf.offset().top >= $("#footer-wrapper").offset().top - 36) {
                        _0xeb1cxf.addClass("on-footer");
                    } else {
                        _0xeb1cxf.removeClass("on-footer");
                    }
                });
                _0xeb1cxf.on("click", function() {
                    $("html, body").animate({
                        scrollTop: 0
                    }, 500);
                });
            });
        });
        //]]>
    </script>
    <script>
        //<![CDATA[
        $("#freebify-preview-main-before-ad .widget").each(function() {
            var e = $(this);
            e.length && e.appendTo($("#before-ad"))
        }), $("#freebify-preview-main-after-ad").each(function() {
            var e = $(this);
            e.length && e.appendTo($("#after-ad"))
        })
        //]]>
    </script>
    <script>
        $(window).scroll(function() {
            if ($(this).scrollTop() > 200) {
                $('#back-to-top').fadeIn();
            } else {
                $('#back-to-top').fadeOut();
            }
        });
        $('#back-to-top').hide().click(function() {
            $('html, body').animate({
                scrollTop: 0
            }, 1000);
            return false;
        });
    </script>
    <script>
        //<![CDATA[
        /*
         Sticky-kit v1.1.2 | WTFPL | Leaf Corcoran 2015 | http://leafo.net
        */
        (function() {
            var b, f;
            b = this.jQuery || window.jQuery;
            f = b(window);
            b.fn.stick_in_parent = function(d) {
                var A, w, J, n, B, K, p, q, k, E, t;
                null == d && (d = {});
                t = d.sticky_class;
                B = d.inner_scrolling;
                E = d.recalc_every;
                k = d.parent;
                q = d.offset_top;
                p = d.spacer;
                w = d.bottoming;
                null == q && (q = 0);
                null == k && (k = void 0);
                null == B && (B = !0);
                null == t && (t = "is_stuck");
                A = b(document);
                null == w && (w = !0);
                J = function(a, d, n, C, F, u, r, G) {
                    var v, H, m, D, I, c, g, x, y, z, h, l;
                    if (!a.data("sticky_kit")) {
                        a.data("sticky_kit", !0);
                        I = A.height();
                        g = a.parent();
                        null != k && (g = g.closest(k));
                        if (!g.length) throw "failed to find stick parent";
                        v = m = !1;
                        (h = null != p ? p && a.closest(p) : b("<div />")) && h.css("position", a.css("position"));
                        x = function() {
                            var c, f, e;
                            if (!G && (I = A.height(), c = parseInt(g.css("border-top-width"), 10), f = parseInt(g.css("padding-top"), 10), d = parseInt(g.css("padding-bottom"), 10), n = g.offset().top + c + f, C = g.height(), m && (v = m = !1, null == p && (a.insertAfter(h), h.detach()), a.css({
                                        position: "",
                                        top: "",
                                        width: "",
                                        bottom: ""
                                    }).removeClass(t), e = !0), F = a.offset().top - (parseInt(a.css("margin-top"), 10) || 0) - q,
                                    u = a.outerHeight(!0), r = a.css("float"), h && h.css({
                                        width: a.outerWidth(!0),
                                        height: u,
                                        display: a.css("display"),
                                        "vertical-align": a.css("vertical-align"),
                                        "float": r
                                    }), e)) return l()
                        };
                        x();
                        if (u !== C) return D = void 0, c = q, z = E, l = function() {
                            var b, l, e, k;
                            if (!G && (e = !1, null != z && (--z, 0 >= z && (z = E, x(), e = !0)), e || A.height() === I || x(), e = f.scrollTop(), null != D && (l = e - D), D = e, m ? (w && (k = e + u + c > C + n, v && !k && (v = !1, a.css({
                                    position: "fixed",
                                    bottom: "",
                                    top: c
                                }).trigger("sticky_kit:unbottom"))), e < F && (m = !1, c = q, null == p && ("left" !== r && "right" !== r || a.insertAfter(h),
                                    h.detach()), b = {
                                    position: "",
                                    width: "",
                                    top: ""
                                }, a.css(b).removeClass(t).trigger("sticky_kit:unstick")), B && (b = f.height(), u + q > b && !v && (c -= l, c = Math.max(b - u, c), c = Math.min(q, c), m && a.css({
                                    top: c + "px"
                                })))) : e > F && (m = !0, b = {
                                    position: "fixed",
                                    top: c
                                }, b.width = "border-box" === a.css("box-sizing") ? a.outerWidth() + "px" : a.width() + "px", a.css(b).addClass(t), null == p && (a.after(h), "left" !== r && "right" !== r || h.append(a)), a.trigger("sticky_kit:stick")), m && w && (null == k && (k = e + u + c > C + n), !v && k))) return v = !0, "static" === g.css("position") && g.css({
                                    position: "relative"
                                }),
                                a.css({
                                    position: "absolute",
                                    bottom: d,
                                    top: "auto"
                                }).trigger("sticky_kit:bottom")
                        }, y = function() {
                            x();
                            return l()
                        }, H = function() {
                            G = !0;
                            f.off("touchmove", l);
                            f.off("scroll", l);
                            f.off("resize", y);
                            b(document.body).off("sticky_kit:recalc", y);
                            a.off("sticky_kit:detach", H);
                            a.removeData("sticky_kit");
                            a.css({
                                position: "",
                                bottom: "",
                                top: "",
                                width: ""
                            });
                            g.position("position", "");
                            if (m) return null == p && ("left" !== r && "right" !== r || a.insertAfter(h), h.remove()), a.removeClass(t)
                        }, f.on("touchmove", l), f.on("scroll", l), f.on("resize",
                            y), b(document.body).on("sticky_kit:recalc", y), a.on("sticky_kit:detach", H), setTimeout(l, 0)
                    }
                };
                n = 0;
                for (K = this.length; n < K; n++) d = this[n], J(b(d));
                return this
            }
        }).call(this);
        // search form
        $(function() {
            $('a[href="#searchfs"]').on("click", function(e) {
                e.preventDefault(), $("#searchfs").addClass("open"), $('#searchfs > form > input[type="search"]').focus()
            }), $("#searchfs, #searchfs button.close").on("click keyup", function(e) {
                e.target != this && "close" != e.target.className && 27 != e.keyCode || $(this).removeClass("open")
            })
        });
        // nav menu
        ! function(s) {
            s.fn.menumaker = function(n) {
                var e = s(this),
                    o = s.extend({
                        format: "dropdown",
                        sticky: !1
                    }, n);
                return this.each(function() {
                    s(this).find(".button").on("click", function() {
                        s(this).toggleClass("menu-opened");
                        var n = s(this).next("ul");
                        n.hasClass("open") ? n.slideToggle(150).removeClass("open") : (n.slideToggle(150).addClass("open"), "dropdown" === o.format && n.find("ul").show())
                    }), e.find("li ul").parent().addClass("has-sub"), multiTg = function() {
                        e.find(".has-sub").prepend('<span class="submenu-button"></span>'), e.find(".submenu-button").on("click", function() {
                            s(this).toggleClass("submenu-opened"), s(this).siblings("ul").hasClass("open") ? s(this).siblings("ul").removeClass("open").slideToggle(150) : s(this).siblings("ul").addClass("open").slideToggle(150)
                        })
                    }, "multitoggle" === o.format ? multiTg() : e.addClass("dropdown"), !0 === o.sticky && e.css("position", "fixed")
                })
            }
        }(jQuery),
        function(s) {
            s(document).ready(function() {
                s("#cssmenu").menumaker({
                    format: "multitoggle"
                })
            })
        }(jQuery);
        //]]>
    </script>
    <script>
        //<![CDATA[
        jQuery(document).ready(function() {
            var i = jQuery(window).width();

            function e() {
                jQuery("#sidebar-sticky").stick_in_parent({
                    parent: "#wrapper",
                    offset_top: 70
                })
            }
            i < 768 ? jQuery("#sidebar-sticky").trigger("sticky_kit:detach") : e(), jQuery(window).resize(function() {
                (i = jQuery(window).width()) < 768 ? jQuery("#sidebar-sticky").trigger("sticky_kit:detach") : e()
            })
        });
        //]]>
    </script>
    <!-- Start Aroed Pagination -->
    <script type='text/javascript'>
        //<![CDATA[ /** Written by aroed.blogspot.com **/
        var postperpage = 25;
        var prevpage = '< Previous';
        var numshowpage = 5;
        var nextpage = 'Next >';
        var urlactivepage = location.href;
        var home_page = "/";
        //]]>
    </script>
    <script src='https://cdn.rawgit.com/xomisse/ac8ccfa4b8fb2c26d5cf76270db92201/raw/f957494b1691cce3d5a8cb92e5b4ed57cded9729/pagination.js' type='text/javascript'></script>
    <!-- End Aroed Pagination -->
    <script type='text/javascript'>
        /*! bloggerbyte-Firebase-post-view */
        jQuery.getScript("//cdn.firebase.com/js/client/2.3.2/firebase.js").done(function() {
            $.each($(".post-view[data-id]"), function(e, a) {
                var i = $(a).parent().find("#postviews").addClass("view-load"),
                    t = new Firebase("https://md-count-view.firebaseio.com/pages/id/" + $(a).attr("data-id"));
                t.once("value", function(e) {
                    var o = e.val(),
                        d = !1;
                    null == o && ((o = {}).value = 0, o.url = window.location.href, o.id = $(a).attr("data-id"), d = !0), i.removeClass("view-load").text(o.value), o.value++, "/" != window.location.pathname && (d ? t.set(o) : t.child("value").set(o.value))
                })
            })
        });
    </script>

    <script type="text/javascript" src="https://www.blogger.com/static/v1/widgets/3000588928-widgets.js"></script>
    <script type='text/javascript'>
        window['__wavt'] = 'AOuZoY4bcGOWm9TLHmnuew41RbMLEFJwFg:1753678818606';
        _WidgetManager._Init('//www.blogger.com/rearrange?blogID\x3d2001592501175586361', '//www.nadimrazatv.online/', '2001592501175586361');
        _WidgetManager._SetDataContext([{
            'name': 'blog',
            'data': {
                'blogId': '2001592501175586361',
                'title': 'NadimRazaTV Official-free  live tv Stream platform Bangladesh \ud83c\udde7\ud83c\udde9',
                'url': 'https://www.nadimrazatv.online/',
                'canonicalUrl': 'http://www.nadimrazatv.online/',
                'homepageUrl': 'https://www.nadimrazatv.online/',
                'searchUrl': 'https://www.nadimrazatv.online/search',
                'canonicalHomepageUrl': 'http://www.nadimrazatv.online/',
                'blogspotFaviconUrl': 'https://i.postimg.cc/ZY2S3qgL/photo-6071237273250285382-y.jpg',
                'bloggerUrl': 'https://www.blogger.com',
                'hasCustomDomain': true,
                'httpsEnabled': true,
                'enabledCommentProfileImages': true,
                'gPlusViewType': 'FILTERED_POSTMOD',
                'adultContent': false,
                'analyticsAccountNumber': '',
                'encoding': 'UTF-8',
                'locale': 'en',
                'localeUnderscoreDelimited': 'en',
                'languageDirection': 'ltr',
                'isPrivate': false,
                'isMobile': false,
                'isMobileRequest': false,
                'mobileClass': '',
                'isPrivateBlog': false,
                'isDynamicViewsAvailable': true,
                'feedLinks': '\x3clink rel\x3d\x22alternate\x22 type\x3d\x22application/atom+xml\x22 title\x3d\x22NadimRazaTV Official-free  live tv Stream platform Bangladesh \ud83c\udde7\ud83c\udde9 - Atom\x22 href\x3d\x22https://www.nadimrazatv.online/feeds/posts/default\x22 /\x3e\n\x3clink rel\x3d\x22alternate\x22 type\x3d\x22application/rss+xml\x22 title\x3d\x22NadimRazaTV Official-free  live tv Stream platform Bangladesh \ud83c\udde7\ud83c\udde9 - RSS\x22 href\x3d\x22https://www.nadimrazatv.online/feeds/posts/default?alt\x3drss\x22 /\x3e\n\x3clink rel\x3d\x22service.post\x22 type\x3d\x22application/atom+xml\x22 title\x3d\x22NadimRazaTV Official-free  live tv Stream platform Bangladesh \ud83c\udde7\ud83c\udde9 - Atom\x22 href\x3d\x22https://www.blogger.com/feeds/2001592501175586361/posts/default\x22 /\x3e\n',
                'meTag': '\x3clink rel\x3d\x22me\x22 href\x3d\x22https://www.blogger.com/profile/18012932550810378007\x22 /\x3e\n',
                'adsenseClientId': 'ca-pub-3311146385229946',
                'adsenseHostId': 'ca-host-pub-1556223355139109',
                'adsenseHasAds': true,
                'adsenseAutoAds': true,
                'boqCommentIframeForm': true,
                'loginRedirectParam': '',
                'view': '',
                'dynamicViewsCommentsSrc': '//www.blogblog.com/dynamicviews/4224c15c4e7c9321/js/comments.js',
                'dynamicViewsScriptSrc': '//www.blogblog.com/dynamicviews/0677bc9f90839fb2',
                'plusOneApiSrc': 'https://apis.google.com/js/platform.js',
                'disableGComments': true,
                'interstitialAccepted': false,
                'sharing': {
                    'platforms': [{
                        'name': 'Get link',
                        'key': 'link',
                        'shareMessage': 'Get link',
                        'target': ''
                    }, {
                        'name': 'Facebook',
                        'key': 'facebook',
                        'shareMessage': 'Share to Facebook',
                        'target': 'facebook'
                    }, {
                        'name': 'BlogThis!',
                        'key': 'blogThis',
                        'shareMessage': 'BlogThis!',
                        'target': 'blog'
                    }, {
                        'name': 'X',
                        'key': 'twitter',
                        'shareMessage': 'Share to X',
                        'target': 'twitter'
                    }, {
                        'name': 'Pinterest',
                        'key': 'pinterest',
                        'shareMessage': 'Share to Pinterest',
                        'target': 'pinterest'
                    }, {
                        'name': 'Email',
                        'key': 'email',
                        'shareMessage': 'Email',
                        'target': 'email'
                    }],
                    'disableGooglePlus': true,
                    'googlePlusShareButtonWidth': 0,
                    'googlePlusBootstrap': '\x3cscript type\x3d\x22text/javascript\x22\x3ewindow.___gcfg \x3d {\x27lang\x27: \x27en\x27};\x3c/script\x3e'
                },
                'hasCustomJumpLinkMessage': false,
                'jumpLinkMessage': 'Read more',
                'pageType': 'index',
                'pageName': '',
                'pageTitle': 'NadimRazaTV Official-free  live tv Stream platform Bangladesh \ud83c\udde7\ud83c\udde9',
                'metaDescription': 'Welcome NadimRaza TV Free Platform 2024_2025_2026'
            }
        }, {
            'name': 'features',
            'data': {}
        }, {
            'name': 'messages',
            'data': {
                'edit': 'Edit',
                'linkCopiedToClipboard': 'Link copied to clipboard!',
                'ok': 'Ok',
                'postLink': 'Post Link'
            }
        }, {
            'name': 'template',
            'data': {
                'name': 'custom',
                'localizedName': 'Custom',
                'isResponsive': true,
                'isAlternateRendering': false,
                'isCustom': true
            }
        }, {
            'name': 'view',
            'data': {
                'classic': {
                    'name': 'classic',
                    'url': '?view\x3dclassic'
                },
                'flipcard': {
                    'name': 'flipcard',
                    'url': '?view\x3dflipcard'
                },
                'magazine': {
                    'name': 'magazine',
                    'url': '?view\x3dmagazine'
                },
                'mosaic': {
                    'name': 'mosaic',
                    'url': '?view\x3dmosaic'
                },
                'sidebar': {
                    'name': 'sidebar',
                    'url': '?view\x3dsidebar'
                },
                'snapshot': {
                    'name': 'snapshot',
                    'url': '?view\x3dsnapshot'
                },
                'timeslide': {
                    'name': 'timeslide',
                    'url': '?view\x3dtimeslide'
                },
                'isMobile': false,
                'title': 'NadimRazaTV Official-free  live tv Stream platform Bangladesh \ud83c\udde7\ud83c\udde9',
                'description': 'Welcome NadimRaza TV Free Platform 2024_2025_2026',
                'url': 'https://www.nadimrazatv.online/',
                'type': 'feed',
                'isSingleItem': false,
                'isMultipleItems': true,
                'isError': false,
                'isPage': false,
                'isPost': false,
                'isHomepage': true,
                'isArchive': false,
                'isLabelSearch': false
            }
        }, {
            'name': 'widgets',
            'data': [{
                'title': '',
                'type': 'HTML',
                'sectionId': 'noti',
                'id': 'HTML1'
            }, {
                'title': '',
                'type': 'HTML',
                'sectionId': 'hero-section',
                'id': 'HTML4'
            }, {
                'title': 'Blog Posts',
                'type': 'Blog',
                'sectionId': 'main',
                'id': 'Blog1',
                'posts': [],
                'headerByline': {
                    'regionName': 'header1',
                    'items': [{
                        'name': 'author',
                        'label': 'by'
                    }, {
                        'name': 'timestamp',
                        'label': '-'
                    }, {
                        'name': 'share',
                        'label': ''
                    }]
                },
                'footerBylines': [{
                    'regionName': 'footer1',
                    'items': [{
                        'name': 'comments',
                        'label': 'Post a Comment'
                    }]
                }, {
                    'regionName': 'footer2',
                    'items': [{
                        'name': 'labels',
                        'label': 'Tags:'
                    }]
                }],
                'allBylineItems': [{
                    'name': 'author',
                    'label': 'by'
                }, {
                    'name': 'timestamp',
                    'label': '-'
                }, {
                    'name': 'share',
                    'label': ''
                }, {
                    'name': 'comments',
                    'label': 'Post a Comment'
                }, {
                    'name': 'labels',
                    'label': 'Tags:'
                }]
            }, {
                'title': 'Contact Form',
                'type': 'ContactForm',
                'sectionId': 'hidden-widgets',
                'id': 'ContactForm1'
            }]
        }]);
        _WidgetManager._RegisterWidget('_HTMLView', new _WidgetInfo('HTML1', 'noti', document.getElementById('HTML1'), {}, 'displayModeFull'));
        _WidgetManager._RegisterWidget('_HTMLView', new _WidgetInfo('HTML4', 'hero-section', document.getElementById('HTML4'), {}, 'displayModeFull'));
        _WidgetManager._RegisterWidget('_BlogView', new _WidgetInfo('Blog1', 'main', document.getElementById('Blog1'), {
            'cmtInteractionsEnabled': false,
            'navMessage': 'No posts.',
            'lightboxEnabled': true,
            'lightboxModuleUrl': 'https://www.blogger.com/static/v1/jsbin/3301882144-lbx.js',
            'lightboxCssUrl': 'https://www.blogger.com/static/v1/v-css/123180807-lightbox_bundle.css'
        }, 'displayModeFull'));
        _WidgetManager._RegisterWidget('_ContactFormView', new _WidgetInfo('ContactForm1', 'hidden-widgets', document.getElementById('ContactForm1'), {
            'contactFormMessageSendingMsg': 'Sending...',
            'contactFormMessageSentMsg': 'Your message has been sent.',
            'contactFormMessageNotSentMsg': 'Message could not be sent. Please try again later.',
            'contactFormInvalidEmailMsg': 'A valid email address is required.',
            'contactFormEmptyMessageMsg': 'Message field cannot be empty.',
            'title': 'Contact Form',
            'blogId': '2001592501175586361',
            'contactFormNameMsg': 'Name',
            'contactFormEmailMsg': 'Email',
            'contactFormMessageMsg': 'Message',
            'contactFormSendMsg': 'Send',
            'contactFormToken': 'AOuZoY54qMIF5If9h7zU9yn-76IGLUzwGQ:1753678818606',
            'submitUrl': 'https://www.blogger.com/contact-form.do'
        }, 'displayModeFull'));
    </script>
</body>

</html>
