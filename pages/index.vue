<template>
  <div class="min-h-screen bg-gray-900 text-white">
    <header class="bg-gray-800 py-4">
      <nav class="container mx-auto">
        <ul class="flex justify-center space-x-8">
          <li><a href="#" class="text-lg hover:text-indigo-400">Home</a></li>
          <li><a href="#" class="text-lg hover:text-indigo-400">Explore</a></li>
          <li><a href="#" class="text-lg hover:text-indigo-400">About</a></li>
          <li><a href="#" class="text-lg hover:text-indigo-400">Contact</a></li>
        </ul>
      </nav>
    </header>



    <main>
      <div class="hero bg-center bg-cover py-40 background-image-dark-forest relative">
        <div class="absolute inset-0 bg-black bg-transparent backdrop-filter backdrop-blur-sm"></div>
          <div class="container mx-auto text-center relative z-10">
            <h1 class="text-5xl font-bold mb-4 text-indigo-400 text-shadow">Welcome to the Forest of Secrets</h1>
            <p class="text-xl mb-8 text-shadow">Unravel the mysteries and embrace the enchanting darkness.</p>
            <a href="#" class="bg-indigo-600 text-white py-3 px-8 rounded-full text-lg hover:bg-indigo-700 transition duration-300">Enter the Forest</a>
          </div>
        </div>

      <div class="features container mx-auto py-20 grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-8">
        <div class="feature text-center">
          <img src="https://img.icons8.com/external-mixed-line-solid-yogi-aprelliyanto/64/000000/external-potion-online-game-mixed-line-solid-yogi-aprelliyanto.png"  alt="Potion Icon" class="feature-icon mx-auto mb-4 w-20 h-20" />
          <h2 class="text-2xl font-semibold mb-2 text-indigo-400">Mystical Potions</h2>
          <p class="text-gray-400">Discover the secrets of ancient potions and their arcane powers.</p>
        </div>
        <div class="feature text-center">
          <img src="https://img.icons8.com/cotton/100/crystal-ball.png"  alt="Crystal Ball Icon" class="feature-icon mx-auto mb-4 w-20 h-20" />
          <h2 class="text-2xl font-semibold mb-2 text-indigo-400">Fortune Telling</h2>
          <p class="text-gray-400">Peer into the crystal ball and unveil your destiny.</p>
        </div>
        <div class="feature text-center">
          <img src="https://img.icons8.com/external-prettycons-lineal-color-prettycons/100/external-magic-book-astrology-and-symbology-prettycons-lineal-color-prettycons.png"  alt="Spell Book Icon" class="feature-icon mx-auto mb-4 w-20 h-20" />
          <h2 class="text-2xl font-semibold mb-2 text-indigo-400">Ancient Spells</h2>
          <p class="text-gray-400">Uncover the forgotten spells and harness their mystical power.</p>
        </div>
      </div>
    </main>

    <footer class="bg-gray-800 py-6">
      <div class="container mx-auto text-center">
        <p class="text-gray-400">&copy; 2024 Forest of Secrets. All rights reserved.</p>
      </div>
    </footer>
  </div>
</template>

<script>
export default {
  mounted() {
    // Add JavaScript interactivity here
    const hero = document.querySelector('.hero');
    
    // Parallax effect on hero background
    window.addEventListener('scroll', () => {
      const scrollPosition = window.pageYOffset;
      hero.style.backgroundPositionY = `${scrollPosition * 0.5}px`;
    });
    
    // Fade-in effect on features
    const features = document.querySelectorAll('.feature');
    
    const observerOptions = {
      root: null,
      threshold: 0.2,
    };
    
    const observerCallback = (entries, observer) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          entry.target.classList.add('opacity-100', 'translate-y-0');
        }
      });
    };
    
    const observer = new IntersectionObserver(observerCallback, observerOptions);
    
    features.forEach((feature) => {
      observer.observe(feature);
      feature.classList.add('opacity-0', 'translate-y-10', 'transition', 'duration-700', 'ease-out');
    });
  },
};
</script>


<style>
.background-image-dark-forest {
  background-image: url('assets/images/dark-forest-4.webp');
  background-size: cover;
  background-repeat: calc(100vh - 100%);
}

.text-shadow {
  text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.6);
}
</style>