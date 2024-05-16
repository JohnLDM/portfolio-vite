<script>
export default {
  name: 'Header',
  data() {
    return {
      menus: [
        {
          name: 'home',
          link: '#home',
        },
        {
          name: 'about me',
          link: '#about',
        },
        {
          name: 'projects',
          link: '#projects',
        },
        {
          name: 'contacts',
          link: '#contacts',
        },
      ],
    };
  },
  methods: {},
};
</script>

<template>
  <header class="row mx-0 py-2">
    <div
      class="custom-container col-10 col-sm-11 d-flex justify-content-between px-0 align-items-center"
    >
      <!-- logo small -->
      <div class="sx d-sm-none">
        <a href="" class="cont-img">
          <img src="/img/logo/logo-small.png" alt="logo" />
        </a>
      </div>

      <!-- logo big -->
      <div class="sx d-none d-sm-block">
        <a href="" class="cont-img">
          <img src="/img/logo/logo-big.png" alt="logo" />
        </a>
      </div>

      <div class="dx d-flex align-items-center">
        <a
          href="#contacts"
          class="custom-btn text-uppercase me-5 d-none d-md-block"
          >get in touch</a
        >

        <!-- <button class="custom-btn text-uppercase" type="button">menu</button> -->

        <!-- OFFCANVAS -->
        <button
          class="custom-btn text-uppercase"
          type="button"
          data-bs-toggle="offcanvas"
          data-bs-target="#offcanvasScrolling"
          aria-controls="offcanvasScrolling"
        >
          menu
        </button>

        <div
          ref="offcanvas"
          class="offcanvas offcanvas-top"
          data-bs-scroll="false"
          data-bs-backdrop="false"
          tabindex="-1"
          id="offcanvasScrolling"
          aria-labelledby="offcanvasScrollingLabel"
        >
          <!-- offcanvas header -->
          <div class="offcanvas-header">
            <div
              class="custom-container col-10 col-sm-11 d-flex justify-content-between px-0 align-items-center"
            >
              <!-- logo small -->
              <div class="sx d-sm-none">
                <a href="" class="cont-img">
                  <img src="/img/logo/logo-small.png" alt="logo" />
                </a>
              </div>

              <!-- logo big -->
              <div class="sx d-none d-sm-block">
                <a href="" class="cont-img">
                  <img src="/img/logo/logo-big.png" alt="logo" />
                </a>
              </div>

              <div class="dx d-flex align-items-center">
                <!-- close btn -->
                <button
                  type="button"
                  class="custom-btn"
                  data-bs-dismiss="offcanvas"
                  aria-label="Close"
                >
                  <i class="fa-solid fa-x"></i>
                </button>
                <!-- close btn /-->
              </div>
            </div>
          </div>
          <!-- offcanvas header /-->

          <!-- offcanvas body -->
          <div class="offcanvas-body">
            <ul class="m-0 p-0">
              <li v-for="menu in menus">
                <a :href="menu.link">
                  <button
                    type="button"
                    data-bs-dismiss="offcanvas"
                    aria-label="Close"
                  >
                    {{ menu.name }}
                  </button>
                </a>
              </li>
            </ul>
          </div>
          <!-- offcanvas body -->
        </div>
        <!-- offcanvas -->
      </div>
    </div>
  </header>
</template>

<style scoped lang="scss">
@use '../assets/scss/style.scss' as *;

header {
  position: fixed;
  top: 0;
  right: 0;
  left: 0;
  z-index: 999;

  .custom-container {
    margin: 0 auto;
    color: #f5f5f5;

    .sx {
      .cont-img {
        height: 100px;

        img {
        }
      }
    }

    .dx {
      .offcanvas-top {
        height: 100vh;
        background-color: var(--custom-primary);

        .offcanvas-body {
          ul {
            list-style-type: none;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: space-around;
            height: 80%;

            button {
              text-transform: uppercase;
              background-color: transparent;
              border: none;
              font-size: clamp(50px, 10vw, 80px);
              color: var(--custom-white);
              font-weight: 800;
              padding: 0;
              position: relative;
              cursor: pointer;

              &:hover {
                color: var(--custom-secondary);
              }
            }
          }
        }
      }
    }
  }
}
</style>
