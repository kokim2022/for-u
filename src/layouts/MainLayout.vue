<template>
  <div class="fixed-center">
    <q-btn
      label="Please Click Me 😘"
      color="pink-5"
      @click="startCountdown"
      rounded
      no-caps
      size="lg"
    />
  </div>

  <q-dialog v-model="showDialog" persistent no-esc-dismiss no-backdrop-dismiss>
    <q-card class="my-card bg-pink-5" style="width: 300px; height: 300px">
      <q-card-section
        class="text-white text-center q-pt-lg"
        style="height: 100px"
      >
        <div class="text-h6">Please Wait My Love 😘</div>
      </q-card-section>
      <q-card-section style="height: 100px">
        <div class="text-h4 text-center">
          {{ currentNumber }}
        </div>
      </q-card-section>
      <q-card-section style="height: 100px">
        <div class="text-center">
          <q-spinner-gears color="cyan" size="xl" />
        </div>
      </q-card-section>
    </q-card>
  </q-dialog>
  <div v-if="showImage" class="fixed-center">
    <q-img src="love_u.webp" class="rounded-borders" style="width: 300px">
    </q-img>
  </div>
</template>

<script>
import { ref } from 'vue';
import { useQuasar } from 'quasar';

export default {
  setup() {
    const $q = useQuasar();
    $q.dark.set(true); // or false or "auto"
    return {
      showDialog: ref(false),
      showImage: ref(false),
    };
  },
  data() {
    return {
      countdownArray: [5, 4, 3, 2, 1],
      currentNumber: 5,
      showCountdown: true,
    };
  },
  methods: {
    startCountdown() {
      this.currentNumber = 5;
      this.showDialog = true;
      let index = 0;
      const countdownInterval = setInterval(() => {
        this.currentNumber = this.countdownArray[index++];
        if (index === this.countdownArray.length + 1) {
          clearInterval(countdownInterval);
          this.showDialog = false;
          this.showImage = true;
        }
      }, 1000);
    },
  },
};
</script>
