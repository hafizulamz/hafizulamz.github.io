<h3>My Playlist</h3>

<style>
    .playlist-card {
        display: block;
        height: 100%;
        padding: 10px;
        border-radius: 8px;
        color: var(--global-text-color);
        text-decoration: none;
        transition: background-color 0.2s ease;
    }
    .playlist-card:hover,
    .playlist-card:focus {
        background-color: rgba(127, 127, 127, 0.12);
        color: var(--global-text-color);
        text-decoration: none;
    }
    .playlist-cover {
        position: relative;
        margin-bottom: 10px;
    }
    .playlist-cover img {
        display: block;
        width: 100%;
        aspect-ratio: 1 / 1;
        object-fit: cover;
        object-position: center 20%;
        border-radius: 6px;
        box-shadow: 0 6px 16px rgba(0, 0, 0, 0.3);
    }
    .playlist-play {
        position: absolute;
        right: 8px;
        bottom: 8px;
        width: 40px;
        height: 40px;
        border-radius: 50%;
        background-color: var(--global-theme-fill-color);
        color: #fff;
        display: flex;
        align-items: center;
        justify-content: center;
        box-shadow: 0 4px 10px rgba(0, 0, 0, 0.35);
        opacity: 0;
        transform: translateY(6px);
        transition: opacity 0.2s ease, transform 0.2s ease;
    }
    .playlist-play svg {
        width: 18px;
        height: 18px;
        margin-left: 2px;
        fill: currentColor;
    }
    .playlist-card:hover .playlist-play,
    .playlist-card:focus .playlist-play {
        opacity: 1;
        transform: translateY(0);
    }
    /* touch screens have no hover, so keep the play button visible */
    @media (hover: none) {
        .playlist-play {
            opacity: 1;
            transform: none;
        }
    }
    .playlist-title {
        font-weight: bold;
        white-space: nowrap;
        overflow: hidden;
        text-overflow: ellipsis;
    }
    .playlist-sub {
        font-size: 0.875em;
        color: var(--global-text-color-light);
    }
</style>

<script>
    document.addEventListener('DOMContentLoaded', function() {
        const links = [
            'https://youtu.be/uWeqeQkjLto',
            'https://youtu.be/gh41Wxez9PE',
            'https://youtu.be/x1yOGhnmYfI',
            'https://youtu.be/ffuPKpaLjLg'
        ];
        function getRandomLink() {
            const randomIndex = Math.floor(Math.random() * links.length);
            return links[randomIndex];
        }
        const anchor = document.getElementById('randomLink');
        anchor.href = getRandomLink();
    });
</script>

{% capture play_icon %}<span class="playlist-play" aria-hidden="true"><svg viewBox="0 0 24 24"><path d="M8 5v14l11-7z"/></svg></span>{% endcapture %}

<div class="row no-gutters">
    <div class="col-6 col-sm-3">
        <a class="playlist-card" href="https://youtu.be/yOOVufv09vk?list=PLCtMYx7FhoE3vAZTbyDVtpn5m8nw_CRVY" target="_blank" rel="noopener noreferrer">
            <div class="playlist-cover"><img src="{{ '/assets/img/joe.jpg' | relative_url }}" alt="Joe Flizzow" loading="lazy">{{ play_icon }}</div>
            <div class="playlist-title">Joe Flizzow</div>
            <div class="playlist-sub">Working playlist</div>
        </a>
    </div>
    <div class="col-6 col-sm-3">
        <a class="playlist-card" href="https://youtu.be/Um7pMggPnug" target="_blank" rel="noopener noreferrer">
            <div class="playlist-cover"><img src="{{ '/assets/img/katyperry.jpg' | relative_url }}" alt="Katy Perry" loading="lazy">{{ play_icon }}</div>
            <div class="playlist-title">Katy Perry</div>
            <div class="playlist-sub">Find the truth in music</div>
        </a>
    </div>
    <div class="col-6 col-sm-3">
        <a class="playlist-card" id="randomLink" href="https://youtu.be/uWeqeQkjLto" target="_blank" rel="noopener noreferrer">
            <div class="playlist-cover"><img src="{{ '/assets/img/jamesblunt.jpg' | relative_url }}" alt="James Blunt" loading="lazy">{{ play_icon }}</div>
            <div class="playlist-title">James Blunt</div>
            <div class="playlist-sub">Hauntingly meaningful</div>
        </a>
    </div>
    <div class="col-6 col-sm-3">
        <a class="playlist-card" href="https://youtu.be/5KNEZJ6KkLI" target="_blank" rel="noopener noreferrer">
            <div class="playlist-cover"><img src="{{ '/assets/img/nickjonas.jpg' | relative_url }}" alt="Nick Jonas" loading="lazy">{{ play_icon }}</div>
            <div class="playlist-title">Nick Jonas</div>
            <div class="playlist-sub">Embrace youth</div>
        </a>
    </div>
</div>
<div class="caption">
    "Where words fail, music speaks." -Hans C. Andersen
</div>
