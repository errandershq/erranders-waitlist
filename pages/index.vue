<template>
  <main>
    <div class="relative isolate overflow-hidden bg-gray-900 h-screen">
      <svg
        class="absolute inset-0 -z-10 h-full w-full stroke-white/10 [mask-image:radial-gradient(100%_100%_at_top_right,white,transparent)]"
        aria-hidden="true">
        <defs>
          <pattern id="983e3e4c-de6d-4c3f-8d64-b9761d1534cc" width="200" height="200" x="50%" y="-1"
            patternUnits="userSpaceOnUse">
            <path d="M.5 200V.5H200" fill="none" />
          </pattern>
        </defs>
        <svg x="50%" y="-1" class="overflow-visible fill-gray-800/20">
          <path d="M-200 0h201v201h-201Z M600 0h201v201h-201Z M-400 600h201v201h-201Z M200 800h201v201h-201Z"
            stroke-width="0" />
        </svg>
        <rect width="100%" height="100%" stroke-width="0" fill="url(#983e3e4c-de6d-4c3f-8d64-b9761d1534cc)" />
      </svg>
      <div
        class="absolute left-[calc(50%-4rem)] top-10 -z-10 transform-gpu blur-3xl sm:left-[calc(50%-18rem)] lg:left-48 lg:top-[calc(50%-30rem)] xl:left-[calc(50%-24rem)]"
        aria-hidden="true">
        <div class="aspect-[1108/632] w-[69.25rem] bg-gradient-to-r from-[#80caff] to-[#4f46e5] opacity-20"
          style="clip-path: polygon(73.6% 51.7%, 91.7% 11.8%, 100% 46.4%, 97.4% 82.2%, 92.5% 84.9%, 75.7% 64%, 55.3% 47.5%, 46.5% 49.4%, 45% 62.9%, 50.3% 87.2%, 21.3% 64.1%, 0.1% 100%, 5.4% 51.1%, 21.4% 63.9%, 58.9% 0.2%, 73.6% 51.7%)">
        </div>
      </div>
      <div class="mx-auto max-w-7xl px-6 pb-24 pt-10 sm:pb-32 lg:flex lg:px-8 lg:py-40">
        <div class="mx-auto max-w-2xl flex-shrink-0 lg:mx-0 lg:max-w-xl lg:pt-8">
          <img class="h-24" src="@/assets/img/logo.png" alt="Your Company">
          <h1 class="mt-10 text-4xl font-bold tracking-tight text-white sm:text-6xl">Erranders: Your Ultimate Campus
            Companion!</h1>
          <p class="mt-6 text-lg leading-8 text-gray-300">Welcome to Erranders, where running errands becomes rewarding!
            Say goodbye to long queues
            and hello to convenience. Join our waitlist now to be among the first to experience a seamless way to handle
            tasks and earn from them. Whether it's picking up lunch from your favorite spot or delivering packages
            across
            campus, Erranders has got you covered. Sign up today and be part of a vibrant community of student
            entrepreneurs shaping the future of campus life!</p>
          <form @submit.prevent="handleSubmit" class="flex items-center gap-x-4">
            <div class="w-full">
              <label for="email" class="block text-sm font-medium leading-6 text-gray-900">Email</label>
              <div class="relative rounded-md shadow-sm">
                <div class="pointer-events-none absolute inset-y-0 left-0 flex items-center pl-3">
                  <svg class="h-5 w-5 text-gray-400" viewBox="0 0 20 20" fill="currentColor" aria-hidden="true">
                    <path d="M3 4a2 2 0 00-2 2v1.161l8.441 4.221a1.25 1.25 0 001.118 0L19 7.162V6a2 2 0 00-2-2H3z" />
                    <path
                      d="M19 8.839l-7.77 3.885a2.75 2.75 0 01-2.46 0L1 8.839V14a2 2 0 002 2h14a2 2 0 002-2V8.839z" />
                  </svg>
                </div>
                <input type="email" name="email" id="email" v-model="formData.email"
                  class="block w-full rounded-md border-0 py-3 pl-10 text-gray-900 ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6"
                  placeholder="you@example.com">
              </div>
            </div>
            <div class="pt-6">
              <button type="button" :disabled="!isFormEmpty || processing"
                class="rounded-md bg-indigo-600 px-3.5 py-2.5 text-sm font-semibold text-white shadow-sm hover:bg-indigo-500 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-600">{{ processing ? 'processing' : 'Submit' }}</button>
            </div>

          </form>
        </div>
        <div class="mx-auto mt-16 flex max-w-2xl sm:mt-24 lg:ml-10 lg:mr-0 lg:mt-0 lg:max-w-none lg:flex-none xl:ml-32">
          <div class="max-w-3xl flex-none sm:max-w-5xl lg:max-w-none">
            <img src="@/assets/img/dashboard.png" alt="App screenshot" width="2432" height="1442"
              class="w-[76rem] rounded-md bg-white/5 shadow-2xl ring-1 ring-white/10">
          </div>
        </div>
      </div>
    </div>

    <CoreBaseModal :show="showModal" @update:show="showModal = $event">
      <section class="max-w-2xl px-3 py-6 mx-auto">
        <main class="mt-8 space-y-6">
          <img class="object-cover w-full h-56 rounded-lg md:h-72"
            src="https://images.unsplash.com/photo-1522071820081-009f0129c71c?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1470&q=80"
            alt="">
          <p class="mt-2 leading-loose text-gray-800 text-sm">
            Hey there Erranders Enthusiast,

            A massive thank you for hopping on board our waitlist! Your interest in Erranders means the world to us, and
            we're beyond thrilled to have you join our journey to revolutionize the way deliveries are made.

            Your support fuels our determination to craft the best possible experience for you and our community. We
            promise to keep you in the loop every step of the way as we work tirelessly to bring Erranders to life.

            Stay tuned for exclusive updates and early access opportunities. We can't wait to embark on this exciting
            adventure together!

            <!-- Cheers, -->
            <!-- 
            Marquis Abah.
            Founder of Erranders. -->
          </p>

          <p class="mt-2 text-gray-800 text-sm">
            Best regards, <br>
            The Erranders Team
          </p>
        </main>
      </section>
    </CoreBaseModal>
  </main>
</template>

<script setup lang="ts">
const processing = ref(false)
const formData = ref({
  email: '',
});

async function handleSubmit() {
  processing.value = true
  const url = 'https://erranders-backend-waitlist.onrender.com/api/auth/signup';  // Your API endpoint
  try {
    const response = await fetch(url, {
      method: 'POST',
      headers: {
        'Content-Type': 'application/json'
      },
      body: JSON.stringify(formData.value)
    });

    if (!response.ok) {
      throw new Error('Network response was not ok.');
    }

    const result = await response.json();
    showModal.value = true
    formData.value.email = ''
  } catch (error) {
    if (process.client) {
      useNuxtApp().$toast('Error submitting form');
    }
  } finally {
    processing.value = false
  }
}

const isFormEmpty = computed(() => {
  return !!(formData.value.email)
})

const showModal = ref(false);
</script>