<script>
export default {
  data() {
    return {
      sectionData: [
      {
        icon: "fa-regular fa-lightbulb", // lampadina
        title: "One to One",
        description: "Getting the necessary clarity about the current state to help you improve your game..",
      },
      {
        icon: "fa-solid fa-map-location", // mappa
        title: "Anywhere",
        description: "Access to valuable and portable program which allow you to setup and live anywhere you want.",
      },
      {
        icon: "fa-solid fa-clock-rotate-left", // orologio
        title: "On Time",
        description: "Punctuality is our top priority because it's an essential criteria to assess a program quality",
      },
      {
        icon: "fa-solid fa-laptop", // laptop
        title: "Online Coures",
        description: "Online business coaching now offers you a very powerful way to empower your business into success.",
      },
      {
        icon: "fa-solid fa-life-ring", // salvagente
        title: "Consulting",
        description: "You will get a clear sense of direction for your business, thorough assessment and faster results.",
      },
      {
        icon: "fa-solid fa-gear", // rotella
        title: "Self Developmenta",
        description: "Business Coaching often keep your focus and develop you both in a professional and personal way.",
      },
    ]
   }
  }
}
</script>

<template>
<section>
  <div class="container">
    <div class="row">
      <div class="col text-center">
        <p class="left-text1">Let’s Dream Big Together</p>
        <p class="left-text2">We are pioneers of the digital approach, using leading-edge
                              technology to simplify procedures and apply executive
                              coaching in the new age of digitalization.
        </p>
        <div class="features-section">
          <div class="feature" v-for="(item, index) in sectionData" :key="index">
            <i :class="item.icon" class="feature-icon"></i>
            <div>
              <h3>{{ item.title }}</h3>
              <p>{{ item.description }}</p>
            </div>
          </div>
        </div>
        <div class="container_button">
          <button class="button-white">
            learn more
          </button>
          <button>
            Get started today
          </button>
        </div>
      </div>
    </div>
  </div>
</section>
</template>

<style lang="scss" scoped>

$primary-color: #61e6d2;
$hover-background: #343142;
$button-border: grey;

.features-section {
  display: flex;
  flex-wrap: wrap;
  text-align: center;
  justify-content: space-between;

  .feature {
    display: flex;
    text-align: left;
    padding: 20px;
    width: calc(33% - 20px);
    transition: transform 0.3s ease;

    &:hover {
      .feature-icon {
        animation: rotate 0.6s forwards;
      }
    }
  }

  .feature-icon {
    font-size: 40px;
    margin: 20px;
    transition: transform 0.3s ease;

    @keyframes rotate {
      from {
        transform: rotate(0deg);
      }
      to {
        transform: rotate(360deg);
      }
    }
  }
}

.container_button {
  padding: 30px;

  .button-white {
    background-color: white;
    color: $primary-color;
    border: $button-border 2px solid;
    transition: background-color 0.3s ease, color 0.3s ease;

    &:hover {
      color: white;
      background-color: $hover-background;
    }
  }

  button {
    transition: background-color 0.3s ease, color 0.3s ease;

    &:hover {
      color: white;
      background-color: $hover-background;
    }
  }
}
</style>