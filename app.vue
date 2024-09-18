<template>

  <div>
    <div class="container-1">
      <div class="hero">
        <div class="navbar">
          <nav>
            <ul>
              <li>
                <input
                  class="invisible"
                  type="text"
                  v-model="scriptText"
                />
                <a class="script" @click="copyScript">
                  <p>Copy Script</p>
                </a>
              </li>
            </ul>
          </nav>
        </div>
        <div class="overlay">
          <h1>Zelda</h1>
        </div>
      </div>
    </div>
    <div class="container-2">
      <div class="services">
        <div class="card">
          <i class="fa-solid fa-bolt"></i>
          <span>Optimization</span>
          <div></div>
          <p>
            This script is well optimized for all the games it supports. Plus it can run on all level 7 and 8 exploits.
          </p>
        </div>
        <div class="card">
          <i class="fa-solid fa-microchip"></i>
          <span>PC and Mobile Support</span>
          <div></div>
          <p>
            This script supports both mobile and PC. Something that very few hubs usually have nowadays.
          </p>
        </div>
      </div>
    </div>
    <div class="footer">Copyright © 2024 Zelda. All rights reserved.</div>
  </div>
</template>
<script setup>
useHead({
  title: 'Cenzo | Get Script',
})
</script>
<script>

export default {
  data() {
    return {
      scriptText: "loadstring(game:HttpGet('https://zalda.xyz/Script/Initialization.lua'))()"
    };
  },
  methods: {
    copyScript() {
      navigator.clipboard.writeText(this.scriptText)
        .then(() => {
          alert("Script was copied correctly");
        })
        .catch((err) => {
          console.error("Error when copying the script: ", err);
        });
    },
    createSnowflake() {
      const snowflake = document.createElement('div');
      snowflake.className = 'snowflake';
      snowflake.style.left = Math.random() * 100 + 'vw';
      snowflake.style.animationDuration = 2 + Math.random() * 4 + 's';
      snowflake.style.animationDelay = Math.random() * 1 + 's';
      snowflake.style.opacity = Math.random() * 0.7 + 0.3;
      document.body.appendChild(snowflake);

      setTimeout(() => {
        snowflake.remove();
      }, (parseFloat(snowflake.style.animationDuration) + parseFloat(snowflake.style.animationDelay)) * 1000);
    }
  },
  mounted() {
    this.snowflakeInterval = setInterval(this.createSnowflake, 100);
  },
  beforeDestroy() {
    clearInterval(this.snowflakeInterval);
  }
}
</script>

<style>
@import 'public/index.css';
</style>
