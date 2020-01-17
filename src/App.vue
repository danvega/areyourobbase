<template>
  <section
    v-for="choice in choices"
    :key="choice.id"
    :id="choice.id"
    :style="{'background-color': choice.background}"
  >
    <div class="choice">
      <div class="question">{{ choice.question }}</div>
      <a v-for="link in choice.links" :key="link" :href="link.href">{{ link.label }}</a>
    </div>
  </section>
  <iframe
    width="0"
    height="0"
    src="https://www.youtube.com/embed/phOW-CZJWT0?autoplay=1"
    frameborder="0"
    allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture"
    allowfullscreen
  ></iframe>
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
          background: "red"
        },
        {
          id: 2,
          question: "Did you come to get down?",
          links: [
            { href: "#3", label: "Yes" },
            { href: "#6", label: "No" }
          ],
          background: "blue"
        },
        {
          id: 3,
          question: "Are you internationally known?",
          links: [
            { href: "#6", label: "Yes" },
            { href: "#4", label: "No" }
          ],
          background: "purple"
        },
        {
          id: 4,
          question: "Are you known to rock a microphone?",
          links: [
            { href: "#5", label: "Yes" },
            { href: "#6", label: "No" }
          ],
          background: "black"
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
@import "https://fonts.googleapis.com/css?family=Indie+Flower&display=swap";

html {
  scroll-behavior: smooth;
}
body {
  margin: 0;
  padding: 0;
}
section {
  width: 100vw;
  height: 100vh;
  font-family: "Indie Flower", cursive;
  display: flex;
}
.choice {
  width: 50%;
  height: 20%;
  margin: auto;
  border: 3px solid white;
  text-align: center;
}
.question {
  font-size: 50px;
  color: #fff;
  padding: 40px;
}
.choice a {
  color: #fff;
  font-size: 30px;
  padding-right: 20px;
}
iframe {
  display: none;
}
</style>
