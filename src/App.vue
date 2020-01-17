<template>
  <section
    v-for="choice in choices"
    :key="choice.id"
    :id="choice.id"
    :style="{'background-color': choice.background}"
  >
    <div class="choice">
      <div class="question">{{ choice.question }}</div>
      <a
        v-for="link in choice.links"
        :key="link"
        :href="link.href"
        :style="{color: choice.background }"
      >{{ link.label }}</a>
    </div>
  </section>
  <!-- <iframe
    width="0"
    height="0"
    src="https://www.youtube.com/embed/phOW-CZJWT0?autoplay=0"
    frameborder="0"
    allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture"
    allowfullscreen
  ></iframe>-->
</template>

<script>
export default {
  data() {
    return {
      currentChoice: 0,
      choices: [
        {
          id: 1,
          question: "Do you wanna rock right now?",
          links: [
            { href: "#2", label: "Yes" },
            { href: "#6", label: "No" }
          ],
          background: "#FF5F45"
        },
        {
          id: 2,
          question: "Did you come to get down?",
          links: [
            { href: "#3", label: "Yes" },
            { href: "#6", label: "No" }
          ],
          background: "#0698ED"
        },
        {
          id: 3,
          question: "Are you internationally known?",
          links: [
            { href: "#6", label: "Yes" },
            { href: "#4", label: "No" }
          ],
          background: "#FC6C7C"
        },
        {
          id: 4,
          question: "Are you known to rock a microphone?",
          links: [
            { href: "#5", label: "Yes" },
            { href: "#6", label: "No" }
          ],
          background: "#FEC501"
        },
        {
          id: 5,
          question: "You are Rob Base!",
          links: [{ href: "#", label: "Start Over" }],
          background: "black"
        },
        {
          id: 6,
          question: "You are not Rob Base",
          links: [{ href: "#", label: "Start Over" }],
          background: "black"
        }
      ]
    };
  }
};
</script>
<style>
@import "https://fonts.googleapis.com/css?family=Indie+Flower,Public+Sans&display=swap";

* {
  box-sizing: border-box;
}
html {
  scroll-behavior: smooth;
}
body {
  margin: 0;
  padding: 0;
}
section {
  height: 100vh;
  width: 100%;
  display: flex;
}
.choice {
  width: 50%;
  margin: auto;
  border: 3px solid white;
  text-align: center;
  padding: 40px;
}
.question {
  font-size: 50px;
  color: #fff;
  font-family: "Indie Flower", cursive;
  margin-bottom: 20px;
}
.choice a {
  color: #fff;
  font-size: 30px;
  padding-right: 20px;
  font-family: "Public Sans", sans-serif;
  background-color: #fff;
  margin: 5px;
  text-align: center;
  padding: 10px;
  text-decoration: none;
  border-radius: 4px;
}
iframe {
  display: none;
}
</style>
