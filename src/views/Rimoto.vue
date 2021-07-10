<template>
  <div class="h-screen bg-gray-700">
    <!--  ModalForm for Connecting. -->
    <div
      class="
        absolute
        inset-0
        z-50
        bg-black bg-opacity-70
        flex
        items-center
        justify-center
      "
      v-if="showModal"
    >
      <div class="bg-white rounded-sm w-11/12 overflow-hidden">
        <div class="bg-gray-700 p-1">
          <h1 class="font-semibold text-center text-white">RIMOTO Connect</h1>
        </div>
        <div class="p-3 mt-4">
          <div>
            <input
              class="
                w-full
                bg-gray-200
                border-2 border-blue-500
                p-2
                focus:outline-none
              "
              type="text"
              placeholder="Local IP of computer."
              v-model="serverIp"
            />
          </div>
          <button
            class="
              btn
              bg-blue-500
              font-semibold
              uppercase
              text-sm text-white
              mt-4
              mb-4
            "
            @click="connectToSocket()"
          >
            Connect Now
          </button>
        </div>
      </div>
    </div>
    <!-- Navbar -->
    <nav class="flex items-center justify-between bg-gray-800 p-2">
      <div>
        <h1 class="text-md uppercase font-semibold text-white tracking-wider">
          Rimoto
        </h1>
      </div>
      <div class="flex items-center space-x-2" @click="connectToSocket()">
        <span
          :class="socket ? 'bg-green-500' : 'bg-red-500'"
          class="w-3 h-3 rounded-full inline-block"
        >
        </span>
        <span
          :class="socket ? 'text-green-500' : 'text-red-500'"
          class="text-sm uppercase font-semibold tracking-wider"
        >
          {{ socket ? "CONNECTED" : "CLOSED" }}
        </span>
      </div>
    </nav>
    <!-- Media Controller Bar. -->
    <div
      class="bg-gray-800 p-2 flex items-center justify-center mt-4 space-x-3"
    >
      <button @click="sendCommand('volume_up')">
        <fa class="btn-icon" icon="volume-up" />
      </button>
      <button @click="sendCommand('volume_down')">
        <fa class="btn-icon" icon="volume-mute" />
      </button>
      <button @click="sendCommand('backward')">
        <fa class="btn-icon" icon="backward" />
      </button>
      <button @click="sendCommand('playpause')">
        <fa class="btn-icon" icon="play-circle" />
      </button>
      <button @click="sendCommand('forward')">
        <fa class="btn-icon" icon="forward" />
      </button>
      <button @click="sendCommand('speed_down')">
        <fa class="btn-icon" icon="skiing-nordic" />
      </button>
      <button @click="sendCommand('speed_up')">
        <fa class="btn-icon" icon="skiing" />
      </button>
    </div>

    <!-- Other Controlles -->
    <div class="p-2 flex items-stretch justify-between mt-4">
      <div class="bg-gray-800 p-4 m-4 rounded-md">
        <div class="flex justify-center">
          <button @click="sendCommand('up')">
            <fa class="btn-icon bg-gray-900 rounded-full" icon="arrow-alt-circle-up" />
          </button>
        </div>
        <div class="flex space-x-8 justify-center items-center">
          <button @click="sendCommand('left')">
            <fa class="btn-icon bg-gray-900 rounded-full" icon="arrow-alt-circle-left" />
          </button>
          <button @click="sendCommand('right')">
            <fa class="btn-icon bg-gray-900 rounded-full" icon="arrow-alt-circle-right" />
          </button>
        </div>
        <div class="flex justify-center">
          <button @click="sendCommand('down')">
            <fa class="btn-icon bg-gray-900 rounded-full" icon="arrow-alt-circle-down" />
          </button>
        </div>
      </div>

      <div class="bg-gray-800 p-4 m-4 rounded-md relative">
        <div class="flex justify-center space-x-6">
          <button @click="sendCommand('open_music')">
            <fa class="btn-icon bg-gray-900 rounded-full" icon="music" />
          </button>
          <button @click="sendCommand('open_news')">
            <fa class="btn-icon bg-gray-900 rounded-full" icon="newspaper" />
          </button>
        </div>
        <div class="flex space-x-8 justify-center items-center absolute bottom-0 left-0 right-0 mb-4">
          <button @click="sendCommand('left')">
            <fa class="btn-icon bg-gray-900 rounded-full" icon="arrow-alt-circle-left" />
          </button>
          <button @click="sendCommand('right')">
            <fa class="btn-icon bg-gray-900 rounded-full" icon="arrow-alt-circle-right" />
          </button>
        </div>
      </div>
    </div>

    <div
      class="bg-gray-800 p-2 flex items-stretch justify-center mt-4 space-x-3"
    >
      <input 
        type="text" 
        class="flex-1 p-2 focus:outline-none" 
        @input="sendKey($event)"
        autocomplete="off"
      />
      <button 
        @click="sendCommand('enter')" 
        class="font-bold text-white px-3 bg-gray-900"
      >
        En
      </button>
      <button 
        @click="sendCommand('backspace')"
        class="font-bold text-white px-3 bg-gray-900"
      >
        <fa icon="backspace" />
      </button>
    </div>
    <br><br>
    <div>
      <h1 class="text-white font-bold ml-4">
        CPU: {{cpuPercent}} %
      </h1>
      <div class="mx-2 relative p-4 bg-gray-800 rounded-md overflow-hidden">
        <div 
          class="absolute left-0 top-0 bottom-0 bg-blue-500 transition-all  ease-in-out duration-100"
          :style="{width: cpuPercent + '%'}"
        ></div>
      </div>
    </div>
    <br>
    <h1 class="text-white font-bold ml-4">
        RAM: {{ramPercent}} %
    </h1>
    <div>
      <div class="mx-2 relative p-4 bg-gray-800 rounded-md overflow-hidden">
        <div 
          class="absolute left-0 top-0 bottom-0 bg-green-500 transition-all  ease-in-out duration-100"
          :style="{width: ramPercent + '%'}"
        ></div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Rimoto",
  data() {
    return {
      socket: null,
      serverIp: "",
      showModal: false,
      cpuPercent: '',
      ramPercent: ''
    };
  },
  mounted() {
    // Creating the websocket connection.
    const serverIp = localStorage.getItem("serverIp");
    if (serverIp) {
      this.serverIp = serverIp;
    } else {
      this.showModal = true;
    }
    this.connectToSocket();
  },
  methods: {
    connectToSocket() {
      if (!this.socket && this.serverIp) {
        let url = `ws://${this.serverIp}:5678`;
        this.socket = new WebSocket(url);

        this.socket.onopen = () => {
          console.log("Connected");
          localStorage.setItem("serverIp", this.serverIp);
        };
        this.socket.onclose = () => {
          console.log("CLIENT:: Socket Closed.");
          this.socket = null;
        };
        this.socket.onmessage = (e) => {
          const data = JSON.parse(e.data)
          this.ramPercent = parseInt(data.ram)
          this.cpuPercent = parseInt(data.cpu)
        }
        this.showModal = false;
      } else {
        console.log("The socket is connected.");
      }
    },
    sendCommand(cmd) {
      if (!this.socket) {
        console.log("No socket");
      }
      this.socket.send(JSON.stringify({
        type: 'type_keys',
        cmd: cmd
      }));
    },
    sendKey(event) {
      const chars = "QWERTYUIOPASDFGHJKLZXCVBNMqwertyuiopasdfghjklzxcvbnm []{}\\|.,/<>()1234567890!@#$%^^&*-_`"
      if (chars.search(event.data) >= 0) {
        this.socket.send(JSON.stringify({
          type: 'type_key',
          key: event.data
        }))
        console.log("type_key event send", event.data);
      }
      console.log(event.data)
    }
  },
};
</script>

<style lang="postcss" scoped>
@import url("https://fonts.googleapis.com/css2?family=Josefin+Sans:wght@400;500;600;700&display=swap");
* {
  font-family: "Josefin Sans", sans-serif;
}
/* Styles for the rimoto-web */
.btn {
  @apply px-4 py-2 rounded-sm;
}
.btn-icon {
  font-size: 2rem;
  @apply text-gray-200 p-2 focus:outline-none;
}
</style>
