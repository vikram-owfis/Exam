<template>
    <div class="bg-white py-24 sm:py-32">
      <div class="mx-auto max-w-7xl px-6 lg:px-8">
        <div class="mx-auto max-w-4xl text-center">
          <h2 class="text-base font-semibold leading-7 text-indigo-600">
            Pricing
          </h2>
          <p
            class="mt-2 text-4xl font-bold tracking-tight text-gray-900 sm:text-5xl"
          >
            One Pricing for 50 Apps at just ₹999
          </p>
        </div>
        <p
          class="mx-auto mt-6 max-w-2xl text-center text-lg leading-8 text-gray-600"
        >
          Honest pricing. Cancel anytime.
        </p>
        <div class="flex align item-center justify-center mt-4  m-100">
          <p class="px-5">Monthly</p>
        <Switch v-model="enabled" :class="[enabled ? 'bg-indigo-600' : 'bg-gray-200', 'relative inline-flex h-6 w-11 flex-shrink-0 cursor-pointer rounded-full border-2 border-transparent transition-colors duration-200 ease-in-out focus:outline-none focus:ring-2 focus:ring-indigo-600 focus:ring-offset-2']">
      <span class="sr-only">Use setting</span>
      <span aria-hidden="true" :class="[enabled ? 'translate-x-5' : 'translate-x-0', 'pointer-events-none inline-block h-5 w-5 transform rounded-full bg-white shadow ring-0 transition duration-200 ease-in-out']" />
    </Switch>
  <p class="px-5">Yearly</p></div>
        <div
          class="isolate mx-auto mt-16 grid max-w-md grid-cols-1 gap-y-8 sm:mt-20 lg:mx-0 lg:max-w-none lg:grid-cols-3 align-center"
        >
          <div
            v-for="(tier, tierIdx) in tiers"
            :key="tier.id"
            :class="[
              tier.mostPopular ? 'lg:z-10 lg:rounded-b-none' : 'lg:mt-8',
              tierIdx === 0 ? 'lg:rounded-r-none' : '',
              tierIdx === tiers.length - 1 ? 'lg:rounded-l-none' : '',
              'flex flex-col justify-between rounded-3xl bg-white p-8 ring-1 ring-gray-200 xl:p-10',
            ]"
          >
            <div>
              <div class="flex items-center justify-between gap-x-4">
                <h3
                  :id="tier.id"
                  :class="[
                    tier.mostPopular ? 'text-indigo-600' : 'text-gray-900',
                    'text-lg font-semibold leading-8',
                  ]"
                >
                  {{ tier.name }}
                </h3>
                <p
                  v-if="tier.mostPopular"
                  class="rounded-full bg-indigo-600/10 px-2.5 py-1 text-xs font-semibold leading-5 text-indigo-600"
                >
                 Recommended
                </p>
              </div>
              <p class="mt-4 text-sm leading-6 text-gray-600">
                {{ tier.description }}
              </p>
              <p class="mt-6 flex items-baseline gap-x-1">
                <span class="text-4xl font-bold tracking-tight text-gray-900">{{
                  tier.priceMonthly
                }}</span>
                <span class="text-sm font-semibold leading-6 text-gray-600"
                  >/month</span
                >
              </p>
              <ul
                role="list"
                class="mt-8 space-y-3 text-sm leading-6 text-gray-600"
              >
                <li
                  v-for="feature in tier.features"
                  :key="feature"
                  class="flex gap-x-3"
                >
                  <CheckIcon
                    class="h-6 w-5 flex-none text-indigo-600"
                    aria-hidden="true"
                  />
                  {{ feature }}
                </li>
              </ul>
            </div>
            <a v-if="tier.name!='Hosted'"
              :href="tier.href"
              :aria-describedby="tier.id"
              :class="[
                tier.mostPopular
                  ? 'bg-indigo-600 text-white shadow-sm hover:bg-indigo-500'
                  : 'text-indigo-600 ring-1 ring-inset ring-indigo-200 hover:ring-indigo-300',
                'mt-8 block rounded-md py-2 px-3 text-center text-sm font-semibold leading-6 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-600',
              ]"
              >Sign Up
              <h1 class="text-white-500">14-days trial</h1>
              </a
            >
            <p v-else>
              <p class="text-Yellow-900 px-10 align-item-center">Bring Your Own Server</p>
              <a 
              :href="tier.href"
              :aria-describedby="tier.id"
              :class="[
                tier.mostPopular
                  ? 'bg-indigo-600 text-white shadow-sm hover:bg-indigo-500'
                  : 'text-indigo-600 ring-1 ring-inset ring-indigo-200 hover:ring-indigo-300',
                'mt-8 block rounded-md py-2 px-3 text-center text-sm font-semibold leading-6 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-600',
              ]"
              >Contact Us For SignUp
             </a
            > </p>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  
  <script setup>
import { CheckIcon } from "@heroicons/vue/20/solid";
import { ref } from "vue";
import { Switch } from "@headlessui/vue";

const enabled = ref(false);
const tiers = [
  {
    name: "Cloud",
    id: "tier-Cloud",
    href: "#",
    priceMonthly: "$999",
    description: "The essentials to provide your best work for clients.",
    features: [
      "5 products",
      "Up to 1,000 subscribers",
      "Basic analytics",
      "48-hour support response time",
    ],
    mostPopular: false,
  },
  {
    name: "Enterprise",
    id: "tier-Enterprise",
    href: "#",
    priceMonthly: "$4995",
    description: "A plan that scales with your rapidly growing business.",
    features: [
      "50 apps (Hosted in 6 locations)",
      "99.99% Guaranteed Global Uptime",
      "24/5 Email, Chat and Phone Support",
      "Dedicated Account Representative",
      "Minimum 25 users",
      `Personalized Onboarding`,
      `
  White Label ?`,
      `
  Extra Security and Compliance`,
    ],
    mostPopular: true,
  },
  {
    name: "Hosted",
    id: "tier-Hosted",
    href: "#",
    priceMonthly: "$48",
    description:
      "Use 500apps in your infrastructure for extra security and compliance",
    features: [
      "White Label ?",
      "BYOS (Bring Your Own Server)",
      "Hosted Locally on your Server",
      "100% On-premises Solutions",
      "99.99% Guaranteed Global Uptime",
    ],
    mostPopular: false,
  },
];
</script>