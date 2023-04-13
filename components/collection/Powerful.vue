<template>
  <div class="bg-white py-24 sm:py-32">
    <div class="mx-auto max-w-7xl px-6 lg:px-8">
      <div class="mx-auto max-w-2xl lg:text-center">
        <h2 class="text-base font-semibold leading-7 text-indigo-600">
          Limitless Possibilities. What will you do for your business?
        </h2>
        <p
          class="mt-2 text-3xl font-bold tracking-tight text-gray-900 sm:text-4xl"
        >
          Powerful Features
        </p>
      </div>
      <div class="mx-auto mt-16 max-w-2xl sm:mt-20 lg:mt-24 lg:max-w-none">
        <dl
          class="grid max-w-xl grid-cols-1 gap-x-8 gap-y-16 lg:max-w-none lg:grid-cols-3"
        >
          <div
            v-for="feature in features"
            :key="feature.name"
            class="flex flex-col"
          >
            <dt
              class="flex items-center gap-x-3 text-base font-semibold leading-7 text-gray-900"
            >
              <component
                :is="feature.icon"
                class="h-5 w-5 flex-none text-indigo-600"
                aria-hidden="true"
              />
              {{ feature.name }}
            </dt>
            <dd
              class="mt-4 flex flex-auto flex-col text-base leading-7 text-gray-600"
            >
              <p class="flex-auto">{{ feature.description }}</p>
              <p class="mt-6">
                <a
                  :href="feature.href"
                  class="text-sm font-semibold leading-6 text-indigo-600"
                  >Learn more <span aria-hidden="true">→</span></a
                >
              </p>
            </dd>
          </div>
        </dl>
      </div>
      <div class="flex gap-7">
        <button
          type="button"
          class="gap-8 mt-16 rounded bg-indigo-600 px-3 py-3 text-xs font-semibold text-white shadow-sm hover:bg-indigo-500 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-600"
        >
          signup
        </button>
        <button
          type="button"
          class="gap-8 mt-16 rounded bg-indigo-600 px-3 py-3 text-xs font-semibold text-white shadow-sm hover:bg-indigo-500 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-600"
        >
          explore
        </button>
      </div>
    </div>
  </div>
</template>
  
  <script setup>
import {
  ArrowPathIcon,
  CloudArrowUpIcon,
  LockClosedIcon,
} from "@heroicons/vue/20/solid";

const features = [
  {
    name: "Behaviour Analytics",
    description:
      "Get behavioral data on how people use your website, what they don't like, where people come from, what pages get traffic, and how you can improve their experience by developing your website.",
    href: "#",
    icon: CloudArrowUpIcon,
  },
  {
    name: "Behaviour Analytics",
    description:
      "Get behavioral data on how people use your website, what they don't like, where people come from, what pages get traffic, and how you can improve their experience by developing your website.",
    href: "#",

    icon: LockClosedIcon,
  },
  {
    name: "Behaviour Analytics",
    description:
      "Get behavioral data on how people use your website, what they don't like, where people come from, what pages get traffic, and how you can improve their experience by developing your website.",
    href: "#",
    icon: ArrowPathIcon,
  },
];
</script>