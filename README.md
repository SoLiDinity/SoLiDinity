<style>
  :root {
    --g1: #AEFF00;
    --g2: #44E349;
    --g3: #00D6BA;
    --f1: #FFD414;
    --f2: #FF9100;
    --f3: #FF00E6;
}

html {
    background-color: black;
}

@keyframes background-pan {
    from {
        background-position: 0% center;
    }
    to {
        background-position: -200% center;
    }
}

@keyframes reveal {
    0% {
        opacity: 0%;
        transform: translateY(100%);
    }
    75% {
        opacity: 100%;
        transform: translateY(-0%);
    }
}

body::-webkit-scrollbar {
    display: none;
}

body {
    display: flex;
    background-color: black;
    height: 100vh;
    justify-content: center;
    align-items: center;
    user-select: none;
}

#text {
    animation: reveal 1s ease forwards;
}
  
.line {
    display: flex;
    justify-content: space-between;
}
  
.word {
    text-decoration: none;
    font-size: 5vw;
    font-family: "Rubik", sans-serif;
    margin: 0rem; 
    text-transform: uppercase;
    transition: 0.5s;
}

.line p, .line a{
    display: inline-block;
    color: #AEFF00;
    position: relative;
    z-index: 1;
}

p .cover, a .cover {
    width: 0%;
    height: 93%;
    position: absolute;
    top: 0;
    left: 0;
    background: rgb(174, 255, 0);
    z-index: -1;
    transition: 0.5s;
}

#text:has(.y:hover) .word:not(.y:hover){
    color: rgb(174, 255, 0);
    opacity: 0.2;
    transition: 0.5s;
}

.magic:hover {
    animation: background-pan 4s linear infinite;
    background: linear-gradient( 
        to right,
        var(--g1),
        var(--g1),
        var(--g1),
        var(--g2),
        var(--g3),
        var(--f1),
        var(--f2),
        var(--f3),
        var(--f2),
        var(--f1),
        var(--g2),
        var(--g1),
        var(--g1));
    background-size: 200%;
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    white-space: nowrap;
}

#text:has(.x:hover) .word:not(.y:hover) .cover{
    width: 100%;
}
</style>

<div id="text">
  <div class="line x">
    <p class="word y"><span class="cover"></span>IT</p>
    <p class="word y"><span class="cover"></span>Student</p>
  </div>
  <div class="line x">
    <p class="word y"><span class="cover"></span>Programmer</p>
    <p class="word y"><span class="cover"></span>&</p>
  </div>
  <div class="line x">
    <p class="word y"><span class="cover"></span>Graphic</p>
    <p class="word y"><span class="cover"></span>Design</p>
  </div>
  <div class="line x">
    <a class="word y" href="https://www.instagram.com/leonardo.djp/" target="_blank">
      <span class="magic"><span class="cover"></span>To My Instagram</span>
    </a>
  </div>
</div>
