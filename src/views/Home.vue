<template>
  <div>
    <header class="text-gray-600 body-font">
      <div
        class="
          container
          mx-auto
          flex flex-wrap
          p-5
          flex-col
          md:flex-row
          items-center
        "
      >
        <a
          class="
            flex
            title-font
            font-medium
            items-center
            text-gray-900
            mb-4
            md:mb-0
          "
        >
          <img src="../assets/logo.png" alt="Rimoto" class="w-10 h-10">
          <span class="ml-3 text-xl">Rimoto</span>
        </a>
        <nav
          class="
            md:ml-auto
            flex flex-wrap
            items-center
            text-base
            justify-center
          "
        >
          <a
            href="https://twitter.com/vivekascoder"
            class="mr-5 hover:text-gray-900"
            >Twitter</a
          >
          <a
            href="https://github.com/vivekascoder/rimoto"
            class="mr-5 hover:text-gray-900"
            >Github</a
          >
        </nav>
        <router-link
          class="
            inline-flex
            items-center
            bg-gray-100
            border-0
            py-1
            px-3
            focus:outline-none
            hover:bg-gray-200
            rounded
            text-base
            mt-4
            md:mt-0
          "
          to="/rimoto"
        >
          Rimoto Web
          <svg
            fill="none"
            stroke="currentColor"
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            class="w-4 h-4 ml-1"
            viewBox="0 0 24 24"
          >
            <path d="M5 12h14M12 5l7 7-7 7"></path>
          </svg>
        </router-link>
      </div>
    </header>
    <section class="text-gray-600 body-font">
      <div
        class="
          container
          mx-auto
          flex
          px-5
          py-24
          items-center
          justify-center
          flex-col
        "
      >
        <img
          class="
            lg:w-2/6
            md:w-3/6
            w-5/6
            mb-10
            object-cover object-center
            rounded
          "
          alt="hero"
          src="../assets/rimoto-web.png"
        />
        <div class="text-center lg:w-2/3 w-full">
          <h1
            class="
              title-font
              sm:text-4xl
              text-3xl
              mb-4
              font-medium
              text-gray-900
            "
          >
            Rimoto Web
          </h1>
          <p class="mb-8 leading-relaxed">
            Rimoto web is a platform to communicate with the rimoto program to
            use your phone or any device that can run a web browser for that
            matter which can be a laptop, smart watch etc. Rimoto Allows you to
            use your laptop or computer with your phone.
          </p>
          <div class="flex justify-center">
            <router-link
              class="
                inline-flex
                text-white
                bg-indigo-500
                border-0
                py-2
                px-6
                focus:outline-none
                hover:bg-indigo-600
                rounded
                text-lg
              "
              to="/rimoto"
            >
              Rimoto Web
            </router-link>
            <a
              class="
                ml-4
                inline-flex
                text-gray-700
                bg-gray-100
                border-0
                py-2
                px-6
                focus:outline-none
                hover:bg-gray-200
                rounded
                text-lg
              "
              href="https://github.com/vivekascoder/rimoto"
            >
              Github
            </a>
          </div>
        </div>
      </div>
    </section>

    <section class="text-gray-600 body-font">
      <div class="container px-5 py-24 mx-auto flex flex-wrap">
        <div class="flex flex-wrap w-full">
          <div class="lg:w-2/5 md:w-1/2 md:pr-10 md:py-6">
            <div class="flex relative pb-12">
              <div
                class="
                  h-full
                  w-10
                  absolute
                  inset-0
                  flex
                  items-center
                  justify-center
                "
              >
                <div class="h-full w-1 bg-gray-200 pointer-events-none"></div>
              </div>
              <div
                class="
                  flex-shrink-0
                  w-10
                  h-10
                  rounded-full
                  bg-indigo-500
                  inline-flex
                  items-center
                  justify-center
                  text-white
                  relative
                  z-10
                "
              >
                <svg
                  fill="none"
                  stroke="currentColor"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  class="w-5 h-5"
                  viewBox="0 0 24 24"
                >
                  <path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"></path>
                </svg>
              </div>
              <div class="flex-grow pl-4">
                <h2
                  class="
                    font-medium
                    title-font
                    text-sm text-gray-900
                    mb-1
                    tracking-wider
                  "
                >
                  STEP 1
                </h2>
                <p class="leading-relaxed">
                  Clone the repository with <br>
                  git clone https://github.com/vivekascoder/rimoto <br>
                  Then Install the requirements by <br>
                  pip install -r ./requirements.txt
                </p>
              </div>
            </div>
            <div class="flex relative pb-12">
              <div
                class="
                  h-full
                  w-10
                  absolute
                  inset-0
                  flex
                  items-center
                  justify-center
                "
              >
                <div class="h-full w-1 bg-gray-200 pointer-events-none"></div>
              </div>
              <div
                class="
                  flex-shrink-0
                  w-10
                  h-10
                  rounded-full
                  bg-indigo-500
                  inline-flex
                  items-center
                  justify-center
                  text-white
                  relative
                  z-10
                "
              >
                <svg
                  fill="none"
                  stroke="currentColor"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  class="w-5 h-5"
                  viewBox="0 0 24 24"
                >
                  <path d="M22 12h-4l-3 9L9 3l-3 9H2"></path>
                </svg>
              </div>
              <div class="flex-grow pl-4">
                <h2
                  class="
                    font-medium
                    title-font
                    text-sm text-gray-900
                    mb-1
                    tracking-wider
                  "
                >
                  STEP 2
                </h2>
                <p class="leading-relaxed">
                  Then run the rimoto server by <br>
                  python3 ./rimoto.py
                </p>
              </div>
            </div>
            <div class="flex relative pb-12">
              <div
                class="
                  h-full
                  w-10
                  absolute
                  inset-0
                  flex
                  items-center
                  justify-center
                "
              >
                <div class="h-full w-1 bg-gray-200 pointer-events-none"></div>
              </div>
              <div
                class="
                  flex-shrink-0
                  w-10
                  h-10
                  rounded-full
                  bg-indigo-500
                  inline-flex
                  items-center
                  justify-center
                  text-white
                  relative
                  z-10
                "
              >
                <svg
                  fill="none"
                  stroke="currentColor"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  class="w-5 h-5"
                  viewBox="0 0 24 24"
                >
                  <circle cx="12" cy="5" r="3"></circle>
                  <path d="M12 22V8M5 12H2a10 10 0 0020 0h-3"></path>
                </svg>
              </div>
              <div class="flex-grow pl-4">
                <h2
                  class="
                    font-medium
                    title-font
                    text-sm text-gray-900
                    mb-1
                    tracking-wider
                  "
                >
                  STEP 3
                </h2>
                <p class="leading-relaxed">
                  Open the remoto web, connect to server by it's local IP
                </p>
              </div>
            </div>
            <div class="flex relative pb-12">
              <div
                class="
                  h-full
                  w-10
                  absolute
                  inset-0
                  flex
                  items-center
                  justify-center
                "
              >
                <div class="h-full w-1 bg-gray-200 pointer-events-none"></div>
              </div>
              <div
                class="
                  flex-shrink-0
                  w-10
                  h-10
                  rounded-full
                  bg-indigo-500
                  inline-flex
                  items-center
                  justify-center
                  text-white
                  relative
                  z-10
                "
              >
                <svg
                  fill="none"
                  stroke="currentColor"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  class="w-5 h-5"
                  viewBox="0 0 24 24"
                >
                  <path d="M20 21v-2a4 4 0 00-4-4H8a4 4 0 00-4 4v2"></path>
                  <circle cx="12" cy="7" r="4"></circle>
                </svg>
              </div>
              <div class="flex-grow pl-4">
                <h2
                  class="
                    font-medium
                    title-font
                    text-sm text-gray-900
                    mb-1
                    tracking-wider
                  "
                >
                  FINISH
                </h2>
                <p class="leading-relaxed">
                  That's all, you've the rimoto setup.
                </p>
              </div>
            </div>
          </div>
          <img
            class="
              lg:w-3/5
              md:w-1/2
              object-cover object-center
              rounded-lg
              md:mt-0
              mt-12
            "
            src="../assets/showcase.jpg"
            alt="step"
          />
        </div>
      </div>
    </section>

    <footer class="text-gray-600 body-font">
      <div class="bg-gray-100">
        <div
          class="
            container
            px-5
            py-6
            mx-auto
            flex
            items-center
            sm:flex-row
            flex-col
          "
        >
          <a
            class="
              flex
              title-font
              font-medium
              items-center
              md:justify-start
              justify-center
              text-gray-900
            "
          >
            <img src="../assets/logo.png" alt="Rimoto" class="w-10 h-10">
            <span class="ml-3 text-xl">Rimoto</span>
          </a>
          <p class="text-sm text-gray-500 sm:ml-6 sm:mt-0 mt-4">
            © 2020 vivekascoder —
            <a
              href="https://twitter.com/vivekascoder"
              rel="noopener noreferrer"
              class="text-gray-600 ml-1"
              target="_blank"
              >@vivekascoder</a
            >
          </p>
          <span
            class="
              inline-flex
              sm:ml-auto
              sm:mt-0
              mt-4
              justify-center
              sm:justify-start
            "
          >
            <a class="text-gray-500">
              <svg
                fill="currentColor"
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                class="w-5 h-5"
                viewBox="0 0 24 24"
              >
                <path
                  d="M18 2h-3a5 5 0 00-5 5v3H7v4h3v8h4v-8h3l1-4h-4V7a1 1 0 011-1h3z"
                ></path>
              </svg>
            </a>
            <a class="ml-3 text-gray-500">
              <svg
                fill="currentColor"
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                class="w-5 h-5"
                viewBox="0 0 24 24"
              >
                <path
                  d="M23 3a10.9 10.9 0 01-3.14 1.53 4.48 4.48 0 00-7.86 3v1A10.66 10.66 0 013 4s-4 9 5 13a11.64 11.64 0 01-7 2c9 5 20 0 20-11.5a4.5 4.5 0 00-.08-.83A7.72 7.72 0 0023 3z"
                ></path>
              </svg>
            </a>
            <a class="ml-3 text-gray-500">
              <svg
                fill="none"
                stroke="currentColor"
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                class="w-5 h-5"
                viewBox="0 0 24 24"
              >
                <rect width="20" height="20" x="2" y="2" rx="5" ry="5"></rect>
                <path
                  d="M16 11.37A4 4 0 1112.63 8 4 4 0 0116 11.37zm1.5-4.87h.01"
                ></path>
              </svg>
            </a>
            <a class="ml-3 text-gray-500">
              <svg
                fill="currentColor"
                stroke="currentColor"
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="0"
                class="w-5 h-5"
                viewBox="0 0 24 24"
              >
                <path
                  stroke="none"
                  d="M16 8a6 6 0 016 6v7h-4v-7a2 2 0 00-2-2 2 2 0 00-2 2v7h-4v-7a6 6 0 016-6zM2 9h4v12H2z"
                ></path>
                <circle cx="4" cy="4" r="2" stroke="none"></circle>
              </svg>
            </a>
          </span>
        </div>
      </div>
    </footer>
  </div>
</template>