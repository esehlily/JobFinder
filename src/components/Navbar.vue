<script setup>
import logo from '@/assets/images/favicon.svg';
</script>

<template>
    <nav class="bg-mauve-950 border-b-2 shadow-purple-500 shadow-lg">
      <div class="mx-auto max-w-7xl px-2 sm:px-6 lg:px-8">
        <div class="flex h-20 items-center justify-between">
          <div
            class="flex flex-1 items-center justify-center md:items-stretch md:justify-start"
          >
            <!-- Logo -->
            <a class="flex shrink-0 items-center mr-4" href="index.html">
              <img class="h-10 w-auto" :src="logo" alt="Vue Jobs" />
              <span class="hidden md:block text-white text-2xl font-bold ml-2"
                >Job Finder</span
              >
            </a>
            <div class="md:ml-auto">
              <div class="flex space-x-2">
                <a
                  href="index.html"
                  class="text-white hover:bg-linear-to-bl from-violet-500 to-fuchsia-500 hover:text-white rounded-md px-5 py-2"
                  >Home</a
                >
                <a
                  href="jobs.html"
                  class="text-white hover:bg-linear-to-bl from-violet-500 to-fuchsia-500 hover:text-white rounded-md px-5 py-2"
                  >Jobs</a
                >
                <a
                  href="add-job.html"
                  class="text-white hover:bg-linear-to-bl from-violet-500 to-fuchsia-500 hover:text-white rounded-md px-5 py-2"
                  >Add Job</a
                >
                <!-- <a
                  href="about.html"
                  class="text-white hover:bg-linear-to-bl from-violet-500 to-fuchsia-500 hover:text-white rounded-md px-5 py-2"
                  >About Us</a
                >
                <a
                  href="pricing.html"
                  class="text-white hover:bg-linear-to-bl from-violet-500 to-fuchsia-500 hover:text-white rounded-md px-5 py-2"
                  >Pricing</a
                >
                <a
                  href="features.html"
                  class="text-white hover:bg-linear-to-bl from-violet-500 to-fuchsia-500 hover:text-white rounded-md px-5 py-2"
                  >Features</a
                > -->
              </div>
            </div>
          </div>
        </div>
      </div>
    </nav>
</template>