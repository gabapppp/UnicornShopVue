<template>
  <header class="bg-white">
    <nav class="mx-auto flex max-w-7xl items-center justify-between p-3 lg:px-4" aria-label="Global">
      <div class="flex lg:flex-1">
        <a href="/" class="-m-1.5 p-1.5">
          <span class="sr-only">Unicorn</span>
          <img class="h-12 w-auto" src="../assets/logo.svg" alt="" />
        </a>
      </div>
      <div class="flex lg:hidden">
        <button type="button" class="-m-2.5 inline-flex items-center justify-center rounded-md p-2.5 text-gray-700"
          @click="mobileMenuOpen = true">
          <span class="sr-only">Open main menu</span>
          <Bars3Icon class="h-6 w-6" aria-hidden="true" />
        </button>
      </div>

      <PopoverGroup class="hidden lg:flex lg:gap-x-12">
        <Popover class="relative">
          <PopoverButton class="flex items-center gap-x-1 text-sm font-semibold leading-6 text-gray-900">
            Men
            <ChevronDownIcon class="h-5 w-5 flex-none text-gray-400" aria-hidden="true" />
          </PopoverButton>

          <transition enter-active-class="transition ease-out duration-200" enter-from-class="opacity-0 translate-y-1"
            enter-to-class="opacity-100 translate-y-0" leave-active-class="transition ease-in duration-150"
            leave-from-class="opacity-100 translate-y-0" leave-to-class="opacity-0 translate-y-1">
            <PopoverPanel
              class="absolute -left-8 top-full z-10 mt-3 w-screen max-w-md overflow-hidden rounded-3xl bg-white shadow-lg ring-1 ring-gray-900/5">
              <div class="p-2">
                <div v-for="item in MenProducts" :key="item.name"
                  class="group relative flex items-center gap-x-6 rounded-lg p-1 text-sm leading-6 hover:bg-gray-50">
                  <div
                    class="flex h-11 w-11 flex-none items-center justify-center rounded-lg bg-gray-50 group-hover:bg-white">
                    <component :is="item.icon" class="h-6 w-6 text-gray-600 group-hover:text-indigo-600"
                      aria-hidden="true" />
                  </div>
                  <div class="flex-auto">
                    <a :href="item.href" class="block font-semibold text-gray-900">
                      {{ item.name }}
                      <span class="absolute inset-0" />
                    </a>
                    <p class="mt-1 text-gray-600">{{ item.description }}</p>
                  </div>
                </div>
              </div>
              <div class="divide-x divide-gray-900/5 bg-gray-50">
                <a v-for="item in MenCallsToAction" :key="item.name" :href="item.href"
                  class="flex items-center justify-center gap-x-2.5 p-2 text-sm font-semibold leading-6 text-gray-900 hover:bg-gray-100">
                  <component :is="item.icon" class="h-5 w-5 flex-none text-gray-400" aria-hidden="true" />
                  {{ item.name }}
                </a>
              </div>
            </PopoverPanel>
          </transition>
        </Popover>
        <Popover class="relative">
          <PopoverButton class="flex items-center gap-x-1 text-sm font-semibold leading-6 text-gray-900">
            Women
            <ChevronDownIcon class="h-5 w-5 flex-none text-gray-400" aria-hidden="true" />
          </PopoverButton>

          <transition enter-active-class="transition ease-out duration-200" enter-from-class="opacity-0 translate-y-1"
            enter-to-class="opacity-100 translate-y-0" leave-active-class="transition ease-in duration-150"
            leave-from-class="opacity-100 translate-y-0" leave-to-class="opacity-0 translate-y-1">
            <PopoverPanel
              class="absolute -left-8 top-full z-10 mt-3 w-screen max-w-md overflow-hidden rounded-3xl bg-white shadow-lg ring-1 ring-gray-900/5">
              <div class="p-4">
                <div v-for="item in WomenProducts" :key="item.name"
                  class="group relative flex items-center gap-x-6 rounded-lg p-1 text-sm leading-6 hover:bg-gray-50">
                  <div
                    class="flex h-11 w-11 flex-none items-center justify-center rounded-lg bg-gray-50 group-hover:bg-white">
                    <component :is="item.icon" class="h-6 w-6 text-gray-600 group-hover:text-indigo-600"
                      aria-hidden="true" />
                  </div>
                  <div class="flex-auto">
                    <a :href="item.href" class="block font-semibold text-gray-900">
                      {{ item.name }}
                      <span class="absolute inset-0" />
                    </a>
                    <p class="mt-1 text-gray-600">{{ item.description }}</p>
                  </div>
                </div>
              </div>
              <div class="divide-x divide-gray-900/5 bg-gray-50">
                <a v-for="item in WomenCallsToAction" :key="item.name" :href="item.href"
                  class="flex items-center justify-center gap-x-2.5 p-2 text-sm font-semibold leading-6 text-gray-900 hover:bg-gray-100">
                  <component :is="item.icon" class="h-5 w-5 flex-none text-gray-400" aria-hidden="true" />
                  {{ item.name }}
                </a>
              </div>
            </PopoverPanel>
          </transition>
        </Popover>
        <!-- <Popover class="relative">
          <PopoverButton
            class="flex items-center gap-x-1 text-sm font-semibold leading-6 text-gray-900"
          >
            New Arrival
            <ChevronDownIcon
              class="h-5 w-5 flex-none text-gray-400"
              aria-hidden="true"
            />
          </PopoverButton>

          <transition
            enter-active-class="transition ease-out duration-200"
            enter-from-class="opacity-0 translate-y-1"
            enter-to-class="opacity-100 translate-y-0"
            leave-active-class="transition ease-in duration-150"
            leave-from-class="opacity-100 translate-y-0"
            leave-to-class="opacity-0 translate-y-1"
          >
            <PopoverPanel
              class="absolute -left-8 top-full z-10 mt-3 w-screen max-w-md overflow-hidden rounded-3xl bg-white shadow-lg ring-1 ring-gray-900/5"
            >
              <div class="p-4">
                <div
                  v-for="item in KidProducts"
                  :key="item.name"
                  class="group relative flex items-center gap-x-6 rounded-lg p-1 text-sm leading-6 hover:bg-gray-50"
                >
                  <div
                    class="flex h-11 w-11 flex-none items-center justify-center rounded-lg bg-gray-50 group-hover:bg-white"
                  >
                    <component
                      :is="item.icon"
                      class="h-6 w-6 text-gray-600 group-hover:text-indigo-600"
                      aria-hidden="true"
                    />
                  </div>
                  <div class="flex-auto">
                    <a
                      :href="item.href"
                      class="block font-semibold text-gray-900"
                    >
                      {{ item.name }}
                      <span class="absolute inset-0" />
                    </a>
                    <p class="mt-1 text-gray-600">{{ item.description }}</p>
                  </div>
                </div>
              </div>
              <div
                class="divide-x divide-gray-900/5 bg-gray-50"
              >
                <a
                  v-for="item in KidCallsToAction"
                  :key="item.name"
                  :href="item.href"
                  class="flex items-center justify-center gap-x-2.5 p-2 text-sm font-semibold leading-6 text-gray-900 hover:bg-gray-100"
                >
                  <component
                    :is="item.icon"
                    class="h-5 w-5 flex-none text-gray-400"
                    aria-hidden="true"
                  />
                  {{ item.name }}
                </a>
              </div>
            </PopoverPanel>
          </transition>
        </Popover> -->
        <a href="/new" class="text-sm font-semibold leading-6 text-gray-900">New Arrival</a>
        <a href="/sales" class="text-sm font-semibold leading-6 text-gray-900">Sales</a>
        <a href="/about" class="text-sm font-semibold leading-6 text-gray-900">About Us</a>
      </PopoverGroup>
      <div class="hidden lg:flex lg:flex-1 lg:justify-end space-x-4 space-x-reverse">
        <a href="#" class="text-sm -m-1.5 p-1.5">
          <IconSearch />
        </a>
        <a @click="cartStore.setCartOpen()" class="text-sm -m-1.5 p-1.5">
          <IconCart />
        </a>
        <a v-if="authStore.userIsAuth" href="/profile" class="text-sm font-semibold leading-6 text-gray-900">
          {{ authStore.user.username }}
        </a>
        <a v-if="!authStore.userIsAuth" href="/login" class="text-sm font-semibold leading-6 text-gray-900">Log in <span
            aria-hidden="true">&rarr;</span></a>
        <a v-if="authStore.userIsAuth" @click="authStore.logout()"
          class="text-sm font-semibold leading-6 text-gray-900">Log
          out <span aria-hidden="true">&rarr;</span></a>
      </div>
    </nav>
    <Dialog as="div" class="lg:hidden" @close="mobileMenuOpen = false" :open="mobileMenuOpen">
      <div class="fixed inset-0 z-10" />
      <DialogPanel
        class="fixed inset-y-0 right-0 z-10 w-full overflow-y-auto bg-white px-6 py-6 sm:max-w-sm sm:ring-1 sm:ring-gray-900/10">
        <div class="flex items-center justify-between">
          <a href="#" class="-m-1.5 p-1.5">
            <span class="sr-only">Unicorn</span>
            <img class="h-8 w-auto" src="../assets/logo.svg" alt="" />
          </a>
          <button type="button" class="-m-2.5 rounded-md p-2.5 text-gray-700" @click="mobileMenuOpen = false">
            <span class="sr-only">Close menu</span>
            <XMarkIcon class="h-6 w-6" aria-hidden="true" />
          </button>
        </div>
        <div class="mt-6 flow-root">
          <div class="-my-6 divide-y divide-gray-500/10">
            <div class="space-y-2 py-6">
              <Disclosure as="div" class="-mx-3" v-slot="{ open }">
                <DisclosureButton
                  class="flex w-full items-center justify-between rounded-lg py-2 pl-3 pr-3.5 text-base font-semibold leading-7 text-gray-900 hover:bg-gray-50">
                  Men
                  <ChevronDownIcon :class="[open ? 'rotate-180' : '', 'h-5 w-5 flex-none']" aria-hidden="true" />
                </DisclosureButton>
                <DisclosurePanel class="mt-2 space-y-2">
                  <DisclosureButton v-for="item in [...MenProducts, ...MenCallsToAction]" :key="item.name" as="a"
                    :href="item.href"
                    class="block rounded-lg py-2 pl-6 pr-3 text-sm font-semibold leading-7 text-gray-900 hover:bg-gray-50">
                    {{ item.name }}</DisclosureButton>
                </DisclosurePanel>
              </Disclosure>
              <Disclosure as="div" class="-mx-3" v-slot="{ open }">
                <DisclosureButton
                  class="flex w-full items-center justify-between rounded-lg py-2 pl-3 pr-3.5 text-base font-semibold leading-7 text-gray-900 hover:bg-gray-50">
                  Women
                  <ChevronDownIcon :class="[open ? 'rotate-180' : '', 'h-5 w-5 flex-none']" aria-hidden="true" />
                </DisclosureButton>
                <DisclosurePanel class="mt-2 space-y-2">
                  <DisclosureButton v-for="item in [...WomenProducts, ...WomenCallsToAction]" :key="item.name" as="a"
                    :href="item.href"
                    class="block rounded-lg py-2 pl-6 pr-3 text-sm font-semibold leading-7 text-gray-900 hover:bg-gray-50">
                    {{ item.name }}</DisclosureButton>
                </DisclosurePanel>
                <!-- <DisclosureButton
                  class="flex w-full items-center justify-between rounded-lg py-2 pl-3 pr-3.5 text-base font-semibold leading-7 text-gray-900 hover:bg-gray-50"
                >
                  Unisex
                  <ChevronDownIcon
                    :class="[open ? 'rotate-180' : '', 'h-5 w-5 flex-none']"
                    aria-hidden="true"
                  />
                </DisclosureButton>
                <DisclosurePanel class="mt-2 space-y-2">
                  <DisclosureButton
                    v-for="item in [...products, ...callsToAction]"
                    :key="item.name"
                    as="a"
                    :href="item.href"
                    class="block rounded-lg py-2 pl-6 pr-3 text-sm font-semibold leading-7 text-gray-900 hover:bg-gray-50"
                  >
                    {{ item.name }}</DisclosureButton
                  >
                </DisclosurePanel> -->
              </Disclosure>
              <a href="/new"
                class="-mx-3 block rounded-lg px-3 py-2 text-base font-semibold leading-7 text-gray-900 hover:bg-gray-50">New
                Arrival</a>
              <a href="/sales"
                class="-mx-3 block rounded-lg px-3 py-2 text-base font-semibold leading-7 text-gray-900 hover:bg-gray-50">Sales</a>
              <a href="/about"
                class="-mx-3 block rounded-lg px-3 py-2 text-base font-semibold leading-7 text-gray-900 hover:bg-gray-50">About
                Us</a>
            </div>
            <div class="py-6">
              <a href="/about"
                class="-mx-3 block rounded-lg px-3 py-2.5 text-base font-semibold leading-7 text-gray-900 hover:bg-gray-50">Search</a>
              <a @click="cartStore.setCartOpen()"
                class="-mx-3 block rounded-lg px-3 py-2.5 text-base font-semibold leading-7 text-gray-900 hover:bg-gray-50">Cart</a>
              <a href="/profile" v-if="authStore.userIsAuth"
                class="-mx-3 block rounded-lg px-3 py-2.5 text-base font-semibold leading-7 text-gray-900 hover:bg-gray-50">{{
                  authStore.user.username }}</a>
              <a href="/login" v-if="!authStore.userIsAuth"
                class="-mx-3 block rounded-lg px-3 py-2.5 text-base font-semibold leading-7 text-gray-900 hover:bg-gray-50">Login</a>
              <a v-if="authStore.userIsAuth" @click="authStore.logout()"
                class="-mx-3 block rounded-lg px-3 py-2.5 text-base font-semibold leading-7 text-gray-900 hover:bg-gray-50">Log
                out</a>
            </div>
          </div>
        </div>
      </DialogPanel>
    </Dialog>
  </header>
  <ShopingCart></ShopingCart>
</template>

<script setup>
import IconCart from "./icons/IconCart.vue";
import IconSearch from "./icons/IconSearch.vue";
import { ref } from "vue";
import {
  Dialog,
  DialogPanel,
  Disclosure,
  DisclosurePanel,
  DisclosureButton,
  Popover,
  PopoverGroup,
  PopoverPanel,
  PopoverButton
} from "@headlessui/vue"
import {
  ArrowPathIcon,
  Bars3Icon,
  ChartPieIcon,
  CursorArrowRaysIcon,
  FingerPrintIcon,
  SquaresPlusIcon,
  XMarkIcon,
  ArrowRightCircleIcon,
} from "@heroicons/vue/24/outline";
import {
  ChevronDownIcon,
} from "@heroicons/vue/20/solid";
import ShopingCart from "./ShopingCart.vue";

import { useAuthStore, useCartStore } from '@/stores';

const authStore = useAuthStore();
const cartStore = useCartStore();
const MenProducts = [
  {
    name: "Tees",
    // description: "Get a better understanding of your traffic",
    href: "#",
    icon: ArrowPathIcon,
  },
  {
    name: "Polos",
    // description: "Speak directly to your customers",
    href: "#",
    icon: ArrowPathIcon,
  },
  {
    name: "Shirts",
    // description: "Build strategic funnels that will convert",
    href: "#",
    icon: ArrowPathIcon,
  },

  {
    name: "Sweaters",
    // description: "Build strategic funnels that will convert",
    href: "#",
    icon: ArrowPathIcon,
  },
  {
    name: "Jackets",
    // description: "Connect with third-party tools",
    href: "#",
    icon: ArrowPathIcon,
  },
  {
    name: "Pants",
    // description: "Your customers’ data will be safe and secure",
    href: "#",
    icon: ArrowPathIcon,
  },
  {
    name: "Shorts",
    // description: "Build strategic funnels that will convert",
    href: "#",
    icon: ArrowPathIcon,
  },

];
const MenCallsToAction = [
  { name: "All Men Product", href: "/men", icon: ArrowRightCircleIcon },
];

const WomenProducts = [
  {
    name: "Dress",
    // description: "Get a better understanding of your traffic",
    href: "#",
    icon: ArrowPathIcon,
  },
  {
    name: "Tees",
    // description: "Get a better understanding of your traffic",
    href: "#",
    icon: ArrowPathIcon,
  },
  {
    name: "Polos",
    // description: "Speak directly to your customers",
    href: "#",
    icon: ArrowPathIcon,
  },
  {
    name: "Shirts",
    // description: "Build strategic funnels that will convert",
    href: "#",
    icon: ArrowPathIcon,
  },
  {
    name: "Sweaters",
    // description: "Build strategic funnels that will convert",
    href: "#",
    icon: ArrowPathIcon,
  },
  {
    name: "Jackets",
    // description: "Connect with third-party tools",
    href: "#",
    icon: ArrowPathIcon,
  },
  {
    name: "Pants",
    // description: "Your customers’ data will be safe and secure",
    href: "#",
    icon: ArrowPathIcon,
  },
  {
    name: "Skirt",
    // description: "Get a better understanding of your traffic",
    href: "#",
    icon: ArrowPathIcon,
  },
  {
    name: "Shorts",
    // description: "Build strategic funnels that will convert",
    href: "#",
    icon: ArrowPathIcon,
  },
];

const WomenCallsToAction = [
  { name: "All Women Product", href: "/women", icon: ArrowRightCircleIcon },
];

const mobileMenuOpen = ref(false);
</script>
