<template>
  <div>
    <navTopNav />
    <Nuxt />
    
          <div class="modal" v-if="modal.show">
            <div class="modal">
              <div class="content-modal">
                <div>
                    <button class="button-close" @click="closeModal" >X</button>
                </div>
                <img class="image-in-modal" @click="closeModal" :src="modal.content"  />
              </div>
            </div>
          </div>
        
   <div class="chat">
            <div class="chat-top" @click="toggleChat">Chat</div>

                <div v-if="chatVisible">
                <div class="chat-bottom"></div>
                <input class="chat-input" type="text">
                </div>
              </div>
           
      
  </div>
</template>
<script>

export default {
  name: "NuxtComponent",
   
  data() {
    return {
      chatVisible: false,
      modal: {
        show: false,
        content: null,
      },
    };
  },
  created() {
    this.$nuxt.$on("openModal", ($event) => this.setModal($event));
    this.$nuxt.$on("closeModal", ($event) => this.setModal($event));
  },
  methods: {
    toggleChat(){
      this.chatVisible = !this.chatVisible;
    },
    setModal(e) {
      this.modal.content = e.content;
      this.modal.show = e.state;
    },
    closeModal() {
        const data = {
          state: false,
          content: null,
        };
        this.$nuxt.$emit("closeModal", data);
      },
  },
};
</script>
<style>

a {
  color: black;
  text-decoration: none;
}
.chat {
  position: absolute;
  bottom: 0;
  right: 0;
  padding: 1vw 2vw;
  margin: 2rem;
}
.chat {
  background-color: black;
  color: white;
  font-size: 1.5rem;
  border-radius: 10%;
  cursor: pointer;
  display: flex;
  flex-direction: column;
  position: fixed;
}

.chat-bottom {
  background-color: white;
  padding: 2rem;
  height: 15vh;
  width: 100%;
  margin-left: -2rem;
}
.chat-visible {
  background-color: white;
  color: black;
  font-size: 1.5rem;
  border-radius: 10%;
  cursor: pointer;
}
.chat-input {
  width: 100%;
  padding: 1rem 2rem;
  margin-left: -2rem;
}

.modal {
    display: flex;
    justify-content: center;
    align-items: center;
    position: absolute;
    background-color: rgba(0, 0, 0, 0.5);
    width: 100%;
    height: 100%;
    top: 0;
    left: 0;
  }
  .content-modal {
    display: flex;
    flex-direction: column;
    width: 75%;
    height: 75%;
    background-color: #eee;
    border-radius: 1rem;
    padding: 2rem;
    justify-content: center;
    align-items: center;
  }
  .content {
    margin-left: auto;
    margin-right: auto;
    max-height: 90%;
  }

  .button-close {
        width: 4vw;
        height: 4vw;
        min-height: 30px;
        min-width: 30px;        
        margin-top: 20px;
        margin-right: 20px;
        border-radius: 25%;
        transition-duration: 0.4s;
        font-size: large;
        background-color: rgb(7, 60, 130);
        color: azure;
    }

    .image-in-modal {
      /* width: 80%;
      height: 80%; */
      height: 80%;
      max-width: 100%;
    }
</style>