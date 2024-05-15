<script>
export default {
  name: 'Footer',
  data() {
    return {
      isCopied: false,
      copiedElement: '',
      socials: [
        {
          icon: 'twitter',
          link: 'https://www.linkedin.com/in/john-henric-quimson-973827280/',
        },
        {
          icon: 'github',
          link: 'https://github.com/JohnQuimson',
        },
        {
          icon: 'instagram',
          link: 'https://www.instagram.com/john_qms/',
        },
      ],
    };
  },
  components: {},
  methods: {
    copyToClipboard(text, message) {
      navigator.clipboard
        .writeText(text)
        .then(() => {
          this.isCopied = true;
          this.copiedElement = message;
          setTimeout(() => {
            this.isCopied = false;
            this.copiedElement = '';
          }, 3000);
        })
        .catch((err) => {
          console.error('Errore nel copiare: ', err);
        });
    },
  },
};
</script>

<template>
  <footer>
    <div class="cont text-white">
      <div class="row m-0">
        <div class="cont-left col-12 col-lg-7">
          <h2>Contacts</h2>
          <ul class="d-flex justify-content-around">
            <li>Turin</li>
            <li>•</li>
            <li>Piedmont</li>
            <li>•</li>
            <li>italy</li>
          </ul>
          <ul class="cont-socials">
            <li v-for="social in socials">
              <a :href="social.link" target="_blank">
                <i :class="`fa-brands fa-square-${social.icon}`"></i>
              </a>
            </li>
          </ul>
        </div>
        <div class="cont-right col-12 col-sm-10 col-lg-5 pt-5 pt-lg-4 p-xl-0">
          <!-- copied message -->
          <span v-if="isCopied" class="mt-lg-4 mt-xl-0"
            >{{ copiedElement }} copied
            <i class="fa-regular fa-circle-check"></i
          ></span>

          <!-- first btn -->
          <button @click="copyToClipboard('3201498436', 'Phone')">
            <div class="cont-info-btn">
              <i class="fa-solid fa-phone"></i>
              <p>+39 320 1498436</p>
            </div>
          </button>
          <!-- first btn -->
          <!-- second btn -->
          <button
            @click="copyToClipboard('john.quimson777@gmail.com', 'Email')"
          >
            <div class="cont-info-btn">
              <i class="fa-solid fa-envelope"></i>
              <p>john.quimson777@gmail.com</p>
            </div>
          </button>
          <!-- second btn -->
        </div>
      </div>
    </div>
  </footer>
</template>

<style lang="scss">
@use '../assets/scss/style.scss' as *;

footer {
  background-color: #1f2020;

  .cont {
    padding: clamp(16px, 2vw, 30px) 0;
    width: 80%;
    margin: 0 auto;

    .cont-left {
      h2 {
        text-transform: uppercase;
        color: var(--custom-white);
        font-size: clamp(40px, 7vw, 200px);
        line-height: clamp(70px, 10vw, 200px);
        font-weight: 800;
        text-align: center;
        padding-top: 30px;
      }

      ul {
        display: flex;
        list-style-type: none;
        justify-content: center;
        margin: 0;
        padding: 0;

        li {
          a {
            font-size: clamp(20px, 10vw, 50px);
            padding: clamp(10px, 2vw, 20px);
            color: var(--custom-secondary);

            &:hover {
              color: var(--custom-white);
            }
          }
        }
      }
    }

    .cont-right {
      display: flex;
      justify-content: center;
      align-items: end;
      gap: clamp(20px, 2vw, 50px);
      position: relative;
      margin: 0 auto;
      // padding-top: 50px;

      span {
        position: absolute;
        top: 0;
      }

      button {
        outline: none;
        width: 50%;
        aspect-ratio: 1/1;
        box-shadow: 10px 10px 0 var(--custom-primary);
        background-color: var(--custom-secondary);
        border: none;
        border-radius: 10%;
        // display: flex;
        // flex-direction: column;
        // align-items: center;
        // position: relative;

        &:hover {
          background-color: var(--custom-white);
        }

        &:active {
          transform: translateX(10px) translateY(10px);
          box-shadow: 5px 5px 0 var(--custom-primary);
        }

        .cont-info-btn {
          display: flex;
          flex-direction: column;
          justify-content: center;
          align-items: center;
          gap: 10px;

          i {
            font-size: clamp(28px, 3vw, 50px);
            // position: absolute;
            // top: 50%;
            // left: 50%;
            // transform: translate(-50%, -50%);
          }

          p {
            font-size: 60%;
          }
        }
      }
    }
  }
}
</style>
