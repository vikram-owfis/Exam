<template>
  <div class="bg-white">
    <!-- Header -->
    <header class="absolute inset-x-0 top-0 z-50">
      <nav
        class="mx-auto flex max-w-7xl items-center justify-between p-6 lg:px-8"
        aria-label="Global"
      >
        <div class="flex lg:flex-1">
          <a href="#" class="-m-1.5 p-1.5">
            <span class="sr-only"></span>
            <h1 class="text-lg font-bold text-blue-600">Site Recording</h1>
          </a>
        </div>
        <div class="flex lg:hidden">
          <button
            type="button"
            class="-m-2.5 inline-flex items-center justify-center rounded-md p-2.5 text-gray-700"
            @click="mobileMenuOpen = true"
          >
            <span class="sr-only">Open main menu</span>
            <Bars3Icon class="h-6 w-6" aria-hidden="true" />
          </button>
        </div>
        <div class="hidden lg:flex lg:gap-x-12">
          <a
            v-for="item in navigation"
            :key="item.name"
            :href="item.href"
            class="text-sm font-semibold leading-6 text-gray-900"
            >{{ item.name }}</a
          >
        </div>
        <div class="hidden lg:flex lg:flex-1 lg:justify-end">
          <a href="#" class="text-sm font-semibold leading-6 text-gray-900"
            >Log in <span aria-hidden="true">&rarr;</span></a
          >
        </div>
        <button
          type="button"
          class="rounded-md bg-indigo-600 px-3.5 py-2.5 text-sm font-semibold text-white shadow-sm hover:bg-white-500 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-600"
        >
          signup
        </button>
      </nav>
      <Dialog
        as="div"
        class="lg:hidden"
        @close="mobileMenuOpen = false"
        :open="mobileMenuOpen"
      >
        <div class="fixed inset-0 z-50" />
        <DialogPanel
          class="fixed inset-y-0 right-0 z-50 w-full overflow-y-auto bg-white px-6 py-6 sm:max-w-sm sm:ring-1 sm:ring-gray-900/10"
        >
          <div class="flex items-center justify-between">
            <a href="#" class="-m-1.5 p-1.5">
              <span class="sr-only">Your Company</span>
              <img
                class="h-8 w-auto"
                src="https://tailwindui.com/img/logos/mark.svg?color=indigo&shade=600"
                alt=""
              />
            </a>
            <button
              type="button"
              class="-m-2.5 rounded-md p-2.5 text-gray-700"
              @click="mobileMenuOpen = false"
            >
              <span class="sr-only">Close menu</span>
              <XMarkIcon class="h-6 w-6" aria-hidden="true" />
            </button>
          </div>
          <div class="mt-6 flow-root">
            <div class="-my-6 divide-y divide-gray-500/10">
              <div class="space-y-2 py-6">
                <a
                  v-for="item in navigation"
                  :key="item.name"
                  :href="item.href"
                  class="-mx-3 block rounded-lg px-3 py-2 text-base font-semibold leading-7 text-gray-900 hover:bg-gray-50"
                  >{{ item.name }}</a
                >
              </div>
              <div class="py-6">
                <a
                  href="#"
                  class="-mx-3 block rounded-lg px-3 py-2.5 text-base font-semibold leading-7 text-gray-900 hover:bg-gray-50"
                  >Log</a
                >
              </div>
            </div>
          </div>
        </DialogPanel>
      </Dialog>
    </header>
  </div>
  <!-- //another component -->
  <div class="flex">
    <div class="relative isolate overflow-hidden bg-white py-24 sm:py-32">
      <div
        class="absolute -top-80 left-[max(6rem,33%)] -z-10 transform-gpu blur-3xl sm:left-1/2 md:top-20 lg:ml-20 xl:top-3 xl:ml-56"
        aria-hidden="true"
      >
        <div
          class="aspect-[801/1036] w-[50.0625rem] bg-gradient-to-tr from-[#faf6f8] to-[#89fce3] opacity-30"
          style="
            clip-path: polygon(
              63.1% 29.6%,
              100% 17.2%,
              76.7% 3.1%,
              48.4% 0.1%,
              44.6% 4.8%,
              54.5% 25.4%,
              59.8% 49.1%,
              55.3% 57.9%,
              44.5% 57.3%,
              27.8% 48%,
              35.1% 81.6%,
              0% 97.8%,
              39.3% 100%,
              35.3% 81.5%,
              97.2% 52.8%,
              63.1% 29.6%
            );
          "
        />
      </div>

      <div class="mx-auto max-w-7xl px-6 lg:px-8 ml-52">
        <div class="mx-auto max-w-2xl lg:mx-0">
          <h1
            class="mt-2 text-3xl font-bold tracking-tight text-gray-900 sm:text-4xl"
          >
            Website Recording Software
          </h1>
          <p
            class="text-lg font-semibold leading-8 tracking-tight text-indigo-600 mt-10"
          >
            Join the SaaS Revolution - 50 Apps for ₹999
          </p>
          <div class="mt-10 max-w-2xl">
            <ul role="list" class="mt-8 max-w-xl space-y-8 text-gray-600">
              <li class="flex gap-x-3">
                <CheckCircleIcon
                  class="mt-1 h-5 w-5 flex-none text-indigo-600"
                  aria-hidden="true"
                />
                <span>
                  Track mouse movement, clicks, taps, form fills and scrolling
                  on your website
                </span>
              </li>
              <li class="flex gap-x-3">
                <CheckCircleIcon
                  class="mt-1 h-5 w-5 flex-none text-indigo-600"
                  aria-hidden="true"
                />
                <span>
                  Create advanced rules for limits and when to record
                </span>
              </li>
              <li class="flex gap-x-3">
                <CheckCircleIcon
                  class="mt-1 h-5 w-5 flex-none text-indigo-600"
                  aria-hidden="true"
                />
                <span>
                  Record real actions taken across multiple pages on desktop and
                  mobile
                </span>
              </li>
              <li class="flex gap-x-3">
                <CheckCircleIcon
                  class="mt-1 h-5 w-5 flex-none text-indigo-600"
                  aria-hidden="true"
                />
                <span>
                  Increase conversions by tracking each user session for
                  unlimited websites
                </span>
              </li>
              <li class="flex gap-x-3">
                <CheckCircleIcon
                  class="mt-1 h-5 w-5 flex-none text-indigo-600"
                  aria-hidden="true"
                />
                <span>
                  Add built-in ConvertPath for hyper personalization
                </span>
              </li>
              <li class="flex gap-x-3">
                <CheckCircleIcon
                  class="mt-1 h-5 w-5 flex-none text-indigo-600"
                  aria-hidden="true"
                />
                <span> Use No-Code BPM software to design workflows </span>
              </li>
            </ul>
          </div>
        </div>
      </div>
      <div
        class="mx-auto mt-16 grid max-w-2xl grid-cols-1 gap-x-8 gap-y-16 lg:mx-0 lg:mt-10 lg:max-w-none lg:grid-cols-12"
      >
        <div class="relative lg:order-last lg:col-span-5">
          <svg
            class="absolute -top-[40rem] left-1 -z-10 h-[64rem] w-[175.5rem] -translate-x-1/2 stroke-gray-900/10 [mask-image:radial-gradient(64rem_64rem_at_111.5rem_0%,white,transparent)]"
            aria-hidden="true"
          >
            <defs>
              <pattern
                id="e87443c8-56e4-4c20-9111-55b82fa704e3"
                width="200"
                height="200"
                patternUnits="userSpaceOnUse"
              >
                <path d="M0.5 0V200M200 0.5L0 0.499983" />
              </pattern>
            </defs>
            <rect
              width="100%"
              height="100%"
              stroke-width="0"
              fill="url(#e87443c8-56e4-4c20-9111-55b82fa704e3)"
            />
          </svg>
        </div>
      </div>
      <!-- footer component -->
      <div class="flex gap-3 ml-96 mr-72">
        <div>
          <button
            type="button"
            class="rounded-md bg-blue-600 px-16 py-5 text-sm font-semibold text-white shadow-sm hover:bg-indigo-500 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-600"
          >
            Sign Up
          </button>
        </div>

        <div class="flex gap-5">
          <div class="text-gray-600 ml-3 mt-3">
            <p>or</p>
          </div>

          <div class="mt-1">
            <img
              class="inline-block h-12 w-12 rounded-full mr-2"
              src="data:image/png;base64,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"
              alt=""
            />

            <img
              class="inline-block h-12 w-12 rounded-full mr-2"
              src="data:image/png;base64,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"
              alt=""
            />

            <img
              class="inline-block h-12 w-12 rounded-full mr-2"
              src="data:image/png;base64,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"
              alt=""
            />

            <img
              class="inline-block h-12 w-12 rounded-full mr-2"
              src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAOEAAADhCAMAAAAJbSJIAAAAclBMVEXz8/PzUyWBvAYFpvD/ugjz9PX19PXz+fr39fr69vPy9fp5uAAAofD/tgDz3Nji6tfzRADzTBfzmYew0oB/xfH70IDX5/P16tfz5eLo7eHzPADzlICs0Hfh6/N3wvH7znj07eEAnvDzvbPL3q6u1/L43q6vy/leAAABd0lEQVR4nO3cR1IDQRREwcb0SEgj770B7n9FNmhEBL1g8zUs8l2gIi9QKUmSpHs5vPtWFV4uANMwunUD3IyiS7+Jebgdx7bddb63uvt+dKOqIBw/xTaZNsLZc3CEhISEhISEhISEhISEhISEhISEhISEhISEhISEhISEhISEhISEhISEhISEhISEhISEhISEhISEhISEhISEhISEhISEhISEhISEhISEhISEhISEjxVuJ7GNfwj7LQjTejcN7noTVu+z4PabgjB1wmumqm50JaAkSX/oLbxmKveiK/zqp8NxHtvx40bMn6dFbKdzgbi81MEdb8LeaRDdqiSsX2Kr541wMXiNjZCQkJCQkJCQkJCQkJCQkJCQkJCQkJCQkJCQkJCQkJCQkJCQkJCQkJCQkJCQkJCQkJCQkJCQkJCQkJCQkJCQkJCQkJCQkJCQkJCQkJCQkJCQkPCxwuj/0kvb/6V5Gd2hmTqvokulm90HluNrFyhJ0j/rC6N0RI28dGy3AAAAAElFTkSuQmCC"
              alt=""
            />
          </div>
        </div>
      </div>
    </div>
    <!-- new one -->
    <div class="mt-80 ml-14 w-96">
      <img
        src="https://ps.w.org/siterecording/assets/banner-772x250.png?rev=2844061"
        alt="Image description"
        class="h-auto w-128"
      />
    </div>
  </div>
  <!-- footer -->
  <CollectionBoundless />
  <CollectionPowerful />
  <CollectionIntegrating />
  <CollectionRupees />
  <CollectionSiteRecording />
  <CollectionFooter />
  <!--  -->
</template>
<script setup>
import {
  CloudArrowUpIcon,
  LockClosedIcon,
  ServerIcon,
} from "@heroicons/vue/20/solid";
import {
  CheckCircleIcon,
  InformationCircleIcon,
} from "@heroicons/vue/20/solid";
import { defineComponent, h, ref } from "vue";
import { Dialog, DialogPanel } from "@headlessui/vue";
import { Bars3Icon, XMarkIcon } from "@heroicons/vue/24/outline";

const navigation = [
  { name: "Product", href: "#" },
  { name: "Features", href: "#" },
  { name: "Resources", href: "#" },
  { name: "Company", href: "#" },
];

const mobileMenuOpen = ref(false);
</script>