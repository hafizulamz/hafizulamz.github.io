<h3>My Playlist</h3>

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

<video width="320" height="240" controls>
  <source src="~/assets/video/James-Blunt-1973-[Simona].mp4" type="video/mp4">
Your browser does not support the video tag.
</video>
</br></br>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/joe.jpg" title="The President" class="img-fluid rounded z-depth-1" %}
        <b>Joe Flizzow</b><br>Working playlist.<br><a href="https://youtu.be/yOOVufv09vk?list=PLCtMYx7FhoE3vAZTbyDVtpn5m8nw_CRVY">Open playlist ></a>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/katyperry.jpg" title="Katy Perry" class="img-fluid rounded z-depth-1" %}
        <b>Katy Perry</b><br>Find the truth in music.<br><a href="https://youtu.be/Um7pMggPnug">Open playlist ></a>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/jamesblunt.jpg" title="James Blunt" class="img-fluid rounded z-depth-1" %}
        <b>James Blunt</b><br>Hauntingly meaningful.<br><a id="randomLink" href="#">Open playlist ></a>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/nickjonas.jpg" title="Nick Jonas" class="img-fluid rounded z-depth-1" %}
        <b>Nick Jonas</b><br>Embrace youth.<br><a href="https://youtu.be/5KNEZJ6KkLI">Open playlist ></a>
    </div>
</div>
<div class="caption">
    "Where words fail, music speaks." -Hans C. Andersen
</div>
