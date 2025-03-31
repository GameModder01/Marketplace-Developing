<template>
  <nav class="bg-white shadow-sm">
    <div class="container mx-auto px-6 py-3">
      <div class="flex items-center justify-between">
        <!-- Left side: Logo and navigation -->
        <div class="flex items-center">
          <!-- Logo -->
          <div class="flex-shrink-0">
            <div class="text-blue-500 h-10 w-10">
              <!-- Simple cartoon-style logo -->
              <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor">
                <path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm0 18c-4.41 0-8-3.59-8-8s3.59-8 8-8 8 3.59 8 8-3.59 8-8 8zm-5-9h10v2H7z" />
              </svg>
            </div>
          </div>

          <!-- Navigation Dropdowns - Desktop -->
          <div class="hidden md:flex items-center space-x-8 ml-8">
            <!-- UI Kits Dropdown -->
            <div class="dropdown relative group">
              <button class="flex items-center text-gray-700 font-light hover:text-blue-500 transition-colors duration-200">
                UI Kits
                <svg class="ml-1 w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"></path>
                </svg>
              </button>
              <div class="dropdown-content bg-white shadow-lg rounded-md py-2 mt-1">
                <a href="#" class="block px-4 py-2 text-sm text-gray-700 hover:bg-gray-100">Basic UI Kit</a>
                <a href="#" class="block px-4 py-2 text-sm text-gray-700 hover:bg-gray-100">Premium UI Kit</a>
                <a href="#" class="block px-4 py-2 text-sm text-gray-700 hover:bg-gray-100">Enterprise UI Kit</a>
              </div>
            </div>

            <!-- Icons Dropdown -->
            <div class="dropdown relative group">
              <button class="flex items-center text-gray-700 font-light hover:text-blue-500 transition-colors duration-200">
                Icons
                <svg class="ml-1 w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"></path>
                </svg>
              </button>
              <div class="dropdown-content bg-white shadow-lg rounded-md py-2 mt-1">
                <a href="#" class="block px-4 py-2 text-sm text-gray-700 hover:bg-gray-100">Line Icons</a>
                <a href="#" class="block px-4 py-2 text-sm text-gray-700 hover:bg-gray-100">Solid Icons</a>
                <a href="#" class="block px-4 py-2 text-sm text-gray-700 hover:bg-gray-100">Duotone Icons</a>
              </div>
            </div>
          </div>
        </div>

        <!-- Right side: Auth and Cart - Desktop -->
        <div class="hidden md:flex items-center space-x-6">
          <a href="#" class="text-gray-700 font-light hover:text-blue-500 transition-colors duration-200">Sign in</a>
          <a href="#" class="text-gray-700 font-light hover:text-blue-500 transition-colors duration-200">Create account</a>
          
          <!-- Shopping Cart -->
          <div class="relative">
            <button class="text-gray-700 hover:text-blue-500 transition-colors duration-200">
              <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M3 3h2l.4 2M7 13h10l4-8H5.4M7 13L5.4 5M7 13l-2.293 2.293c-.63.63-.184 1.707.707 1.707H17m0 0a2 2 0 100 4 2 2 0 000-4zm-8 2a2 2 0 11-4 0 2 2 0 014 0z"></path>
              </svg>
              <span class="absolute -top-1 -right-1 bg-blue-500 text-white text-xs rounded-full h-4 w-4 flex items-center justify-center">
                {{ cartItemCount }}
              </span>
            </button>
          </div>
        </div>

        <!-- Mobile menu button -->
        <div class="md:hidden flex items-center">
          <div class="relative mr-4">
            <button class="text-gray-700 hover:text-blue-500 transition-colors duration-200">
              <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M3 3h2l.4 2M7 13h10l4-8H5.4M7 13L5.4 5M7 13l-2.293 2.293c-.63.63-.184 1.707.707 1.707H17m0 0a2 2 0 100 4 2 2 0 000-4zm-8 2a2 2 0 11-4 0 2 2 0 014 0z"></path>
              </svg>
              <span class="absolute -top-1 -right-1 bg-blue-500 text-white text-xs rounded-full h-4 w-4 flex items-center justify-center">
                {{ cartItemCount }}
              </span>
            </button>
          </div>
          <button @click="toggleMobileMenu" class="text-gray-700 hover:text-blue-500 focus:outline-none">
            <svg v-if="!mobileMenuOpen" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
            </svg>
            <svg v-else class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
            </svg>
          </button>
        </div>
      </div>

      <!-- Mobile Menu -->
      <div v-if="mobileMenuOpen" class="md:hidden mt-4">
        <div class="py-2 border-t border-gray-200">
          <!-- Mobile Navigation Items -->
          <div class="mt-2 space-y-2">
            <!-- UI Kits Dropdown - Mobile -->
            <div class="mobile-dropdown">
              <button @click="toggleDropdown('uiKits')" class="w-full flex items-center justify-between px-2 py-2 text-gray-700 hover:bg-gray-100 rounded">
                <span>UI Kits</span>
                <svg :class="{'transform rotate-180': dropdowns.uiKits}" class="w-4 h-4 transition-transform" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"></path>
                </svg>
              </button>
              <div v-if="dropdowns.uiKits" class="pl-4 py-1 space-y-1">
                <a href="#" class="block px-2 py-1 text-sm text-gray-700 hover:bg-gray-100 rounded">Basic UI Kit</a>
                <a href="#" class="block px-2 py-1 text-sm text-gray-700 hover:bg-gray-100 rounded">Premium UI Kit</a>
                <a href="#" class="block px-2 py-1 text-sm text-gray-700 hover:bg-gray-100 rounded">Enterprise UI Kit</a>
              </div>
            </div>

            <!-- Icons Dropdown - Mobile -->
            <div class="mobile-dropdown">
              <button @click="toggleDropdown('icons')" class="w-full flex items-center justify-between px-2 py-2 text-gray-700 hover:bg-gray-100 rounded">
                <span>Icons</span>
                <svg :class="{'transform rotate-180': dropdowns.icons}" class="w-4 h-4 transition-transform" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"></path>
                </svg>
              </button>
              <div v-if="dropdowns.icons" class="pl-4 py-1 space-y-1">
                <a href="#" class="block px-2 py-1 text-sm text-gray-700 hover:bg-gray-100 rounded">Line Icons</a>
                <a href="#" class="block px-2 py-1 text-sm text-gray-700 hover:bg-gray-100 rounded">Solid Icons</a>
                <a href="#" class="block px-2 py-1 text-sm text-gray-700 hover:bg-gray-100 rounded">Duotone Icons</a>
              </div>
            </div>
          </div>

          <!-- Mobile Auth Links -->
          <div class="mt-4 space-y-2">
            <a href="#" class="block px-2 py-2 text-gray-700 hover:bg-gray-100 rounded">Sign in</a>
            <a href="#" class="block px-2 py-2 text-gray-700 hover:bg-gray-100 rounded">Create account</a>
          </div>
        </div>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  name: 'Navbar',
  data() {
    return {
      cartItemCount: 3,
      mobileMenuOpen: false,
      dropdowns: {
        uiKits: false,
        icons: false
      }
    }
  },
  methods: {
    toggleMobileMenu() {
      this.mobileMenuOpen = !this.mobileMenuOpen;
    },
    toggleDropdown(name) {
      this.dropdowns[name] = !this.dropdowns[name];
    }
  }
}
</script>

<style scoped>
/* Desktop dropdown styles are in the global CSS */
</style>
