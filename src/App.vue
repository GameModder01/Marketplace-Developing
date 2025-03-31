<template>
  <div class="min-h-screen bg-gray-50">
    <Navbar />
    
    <!-- Product Detail Page -->
    <ProductDetail />
    
    <!-- Hero Section -->
    <div class="relative overflow-hidden">
      <!-- Enhanced Background Pattern -->
      <div class="absolute inset-0 bg-gradient-to-br from-blue-50 to-gray-50 opacity-70"></div>
      
      <!-- Modern Animated Background Elements -->
      <div class="absolute -top-24 -right-24 w-96 h-96 bg-gradient-to-br from-blue-100 to-indigo-100 rounded-full blur-3xl opacity-50 animate-pulse"></div>
      <div class="absolute -bottom-24 -left-24 w-96 h-96 bg-gradient-to-br from-indigo-100 to-purple-100 rounded-full blur-3xl opacity-50"></div>
      
      <!-- Floating Product Images -->
      <div class="absolute top-[15%] left-[10%] w-32 h-32 opacity-20 animate-float-product" style="animation-delay: 0s;">
        <img src="data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjAwIiBoZWlnaHQ9IjIwMCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj48cmVjdCB3aWR0aD0iMjAwIiBoZWlnaHQ9IjIwMCIgZmlsbD0iIzFhMmI0NyIgcng9IjEwIiByeT0iMTAiLz48dGV4dCB4PSI1MCIgeT0iODAiIGZvbnQtZmFtaWx5PSJBcmlhbCIgZm9udC1zaXplPSIyNCIgZmlsbD0id2hpdGUiPjMwMCs8L3RleHQ+PHRleHQgeD0iNTAiIHk9IjEyMCIgZm9udC1mYW1pbHk9IkFyaWFsIiBmb250LXNpemU9IjI0IiBmaWxsPSJ3aGl0ZSI+TGluZTwvdGV4dD48dGV4dCB4PSI1MCIgeT0iMTUwIiBmb250LWZhbWlseT0iQXJpYWwiIGZvbnQtc2l6ZT0iMjQiIGZpbGw9IndoaXRlIj5JY29uczwvdGV4dD48L3N2Zz4=" alt="Product" class="w-full h-full object-cover rounded-lg shadow-lg">
      </div>
      
      <div class="absolute top-[60%] left-[75%] w-40 h-40 opacity-15 animate-float-product" style="animation-delay: 2s;">
        <img src="data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjAwIiBoZWlnaHQ9IjIwMCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj48cmVjdCB3aWR0aD0iMjAwIiBoZWlnaHQ9IjIwMCIgZmlsbD0iIzNiNTk5OCIgcng9IjEwIiByeT0iMTAiLz48dGV4dCB4PSI0MCIgeT0iODAiIGZvbnQtZmFtaWx5PSJBcmlhbCIgZm9udC1zaXplPSIzMCIgZmlsbD0id2hpdGUiPlRyYW5zbGF0ZTwvdGV4dD48dGV4dCB4PSI0MCIgeT0iMTIwIiBmb250LWZhbWlseT0iQXJpYWwiIGZvbnQtc2l6ZT0iMTYiIGZpbGw9IndoaXRlIj5jbGVhbiBsYW5ndWFnZSB1aTwvdGV4dD48L3N2Zz4=" alt="Product" class="w-full h-full object-cover rounded-lg shadow-lg">
      </div>
      
      <div class="absolute top-[40%] left-[85%] w-28 h-28 opacity-20 animate-float-product" style="animation-delay: 1s;">
        <img src="data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjAwIiBoZWlnaHQ9IjIwMCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj48cmVjdCB3aWR0aD0iMjAwIiBoZWlnaHQ9IjIwMCIgZmlsbD0iIzFhMmI0NyIgcng9IjEwIiByeT0iMTAiLz48dGV4dCB4PSIyMCIgeT0iODAiIGZvbnQtZmFtaWx5PSJBcmlhbCIgZm9udC1zaXplPSIyMCIgZmlsbD0id2hpdGUiPkFnZW5jeTwvdGV4dD48dGV4dCB4PSIyMCIgeT0iMTEwIiBmb250LWZhbWlseT0iQXJpYWwiIGZvbnQtc2l6ZT0iMjAiIGZpbGw9IndoaXRlIj5UZW1wbGF0ZTwvdGV4dD48L3N2Zz4=" alt="Product" class="w-full h-full object-cover rounded-lg shadow-lg">
      </div>
      
      <div class="absolute top-[70%] left-[15%] w-36 h-36 opacity-15 animate-float-product" style="animation-delay: 3s;">
        <img src="data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjAwIiBoZWlnaHQ9IjIwMCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj48cmVjdCB3aWR0aD0iMjAwIiBoZWlnaHQ9IjIwMCIgZmlsbD0iIzFhMmI0NyIgcng9IjEwIiByeT0iMTAiLz48dGV4dCB4PSIyMCIgeT0iODAiIGZvbnQtZmFtaWx5PSJBcmlhbCIgZm9udC1zaXplPSIxNiIgZmlsbD0id2hpdGUiPnVuaXZlcnNhbCBpY29ucyBmb3I8L3RleHQ+PHRleHQgeD0iMjAiIHk9IjExMCIgZm9udC1mYW1pbHk9IkFyaWFsIiBmb250LXNpemU9IjIwIiBmaWxsPSJ3aGl0ZSI+V2ViICYgTW9iaWxlPC90ZXh0Pjwvc3ZnPg==" alt="Product" class="w-full h-full object-cover rounded-lg shadow-lg">
      </div>
      
      <div class="absolute top-[25%] left-[60%] w-24 h-24 opacity-20 animate-float-product" style="animation-delay: 1.5s;">
        <img src="data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjAwIiBoZWlnaHQ9IjIwMCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj48cmVjdCB3aWR0aD0iMjAwIiBoZWlnaHQ9IjIwMCIgZmlsbD0iIzQ0NDRmZiIgcng9IjEwIiByeT0iMTAiLz48dGV4dCB4PSI1MCIgeT0iMTAwIiBmb250LWZhbWlseT0iQXJpYWwiIGZvbnQtc2l6ZT0iMjQiIGZpbGw9IndoaXRlIj5VSS1LaXQ8L3RleHQ+PC9zdmc+" alt="Product" class="w-full h-full object-cover rounded-lg shadow-lg">
      </div>
      
      <!-- Subtle Geometric Patterns -->
      <div class="absolute top-20 left-1/4 w-64 h-64 border border-blue-200/20 rounded-full animate-slow-spin-reverse"></div>
      <div class="absolute bottom-20 right-1/4 w-48 h-48 border border-indigo-200/20 rounded-full animate-slow-spin" style="animation-delay: 2s;"></div>
      
      <!-- Subtle Grid Pattern -->
      <div class="absolute inset-0 bg-grid-pattern opacity-5"></div>
      
      <!-- Glowing Accent Elements -->
      <div class="absolute top-1/3 right-1/4 w-6 h-6 bg-blue-400 rounded-full blur-sm opacity-20 animate-pulse" style="animation-duration: 3s;"></div>
      <div class="absolute bottom-1/3 left-1/4 w-4 h-4 bg-indigo-400 rounded-full blur-sm opacity-20 animate-pulse" style="animation-duration: 4s; animation-delay: 1s;"></div>
      <div class="absolute top-2/3 right-1/3 w-5 h-5 bg-purple-400 rounded-full blur-sm opacity-20 animate-pulse" style="animation-duration: 5s; animation-delay: 2s;"></div>
      
      <!-- Modern Gradient Overlay -->
      <div class="absolute inset-0 bg-gradient-to-b from-transparent via-blue-50/10 to-transparent"></div>
      
      <!-- Subtle Animated Lines -->
      <div class="absolute top-40 left-0 w-full h-px bg-gradient-to-r from-transparent via-blue-200/30 to-transparent animate-pulse" style="animation-duration: 8s;"></div>
      <div class="absolute top-60 left-0 w-full h-px bg-gradient-to-r from-transparent via-indigo-200/20 to-transparent animate-pulse" style="animation-duration: 12s;"></div>
      
      <!-- Floating Elements with 3D Effect -->
      <div class="absolute top-1/4 left-1/5 w-32 h-32 bg-gradient-to-br from-blue-50/40 to-indigo-50/40 rounded-xl blur-xl transform rotate-12 animate-float-slow"></div>
      <div class="absolute bottom-1/4 right-1/5 w-24 h-24 bg-gradient-to-br from-indigo-50/40 to-purple-50/40 rounded-xl blur-xl transform -rotate-12 animate-float-slow" style="animation-delay: 2s;"></div>
      
      <!-- Content Container -->
      <div class="container relative mx-auto px-6 py-20 md:py-28 text-center">
        <!-- Enhanced Badge with Glassmorphism -->
        <div class="inline-block mb-6 px-4 py-1.5 bg-white/80 backdrop-blur-sm border border-blue-100/50 rounded-full shadow-sm">
          <span class="text-transparent bg-clip-text bg-gradient-to-r from-blue-600 to-indigo-600 font-medium text-sm">Über 10.000 digitale Assets</span>
        </div>
        
        <!-- Enhanced Heading with Modern Typography -->
        <h1 class="text-5xl md:text-6xl font-extrabold text-gray-900 mb-8 tracking-tight leading-tight">
          Your marketplace for high-<br class="hidden sm:block">
          quality <span class="relative inline-block">
            <span class="text-transparent bg-clip-text bg-gradient-to-r from-blue-500 via-indigo-500 to-purple-600 animate-gradient">digital assets</span>
            <span class="absolute -bottom-1 left-0 w-full h-1 bg-gradient-to-r from-blue-500/30 via-indigo-500/30 to-purple-600/30 rounded-full blur-sm"></span>
          </span>.
        </h1>
        
        <!-- Enhanced Description with Better Typography -->
        <p class="text-xl text-gray-600 max-w-3xl mx-auto mb-12 leading-relaxed">
          Welcome to DigitalHippo. Every asset on our platform is verified by our team to 
          ensure our highest quality standards.
        </p>
        
        <!-- Enhanced Buttons with Modern Design -->
        <div class="flex flex-col sm:flex-row justify-center items-center gap-5">
          <a href="#" class="relative overflow-hidden px-8 py-4 bg-gradient-to-r from-blue-500 to-indigo-600 text-white font-medium rounded-lg hover:shadow-xl hover:shadow-blue-200/30 transition-all transform hover:-translate-y-1 group">
            <span class="relative z-10">Browse trending</span>
            <span class="absolute inset-0 bg-gradient-to-r from-blue-600 to-indigo-700 opacity-0 group-hover:opacity-100 transition-opacity"></span>
            <!-- Subtle Button Glow -->
            <span class="absolute -bottom-1 left-1/2 transform -translate-x-1/2 w-4/5 h-4 bg-blue-400 rounded-full blur-md opacity-40"></span>
          </a>
          <a href="#" class="group px-8 py-4 bg-white text-gray-700 font-medium rounded-lg border border-gray-200 hover:border-blue-300 hover:shadow-md hover:shadow-blue-100/40 transition-all flex items-center gap-2">
            Our quality promise 
            <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 group-hover:translate-x-1.5 transition-transform duration-300" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14 5l7 7m0 0l-7 7m7-7H3" />
            </svg>
          </a>
        </div>
        
        <!-- Enhanced Stats Counter with Modern Design -->
        <div class="flex flex-wrap justify-center gap-8 mt-16">
          <div class="text-center">
            <div class="text-3xl font-bold text-gray-900">10,000+</div>
            <div class="text-sm text-gray-500">Digital Assets</div>
          </div>
          <div class="text-center">
            <div class="text-3xl font-bold text-gray-900">8,500+</div>
            <div class="text-sm text-gray-500">Happy Customers</div>
          </div>
          <div class="text-center">
            <div class="text-3xl font-bold text-gray-900">99.9%</div>
            <div class="text-sm text-gray-500">Satisfaction Rate</div>
          </div>
        </div>
      </div>
    </div>
    
    <!-- Brand New Section -->
    <div class="container mx-auto px-6 py-12">
      <div class="flex justify-between items-start mb-6">
        <div>
          <h2 class="text-3xl font-bold text-gray-900">Brand new</h2>
          <p class="text-gray-500 mt-2">Explore more than 10,000 icons and ui kits to use in websites, logos and social media.</p>
        </div>
        <a href="#" class="text-gray-500 hover:text-blue-500 transition-colors">Shop the collection →</a>
      </div>
      
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6">
        <!-- Product Card 1 -->
        <div class="bg-white rounded-lg overflow-hidden shadow-sm hover:shadow-md transition-shadow">
          <div class="relative bg-black aspect-square">
            <div class="absolute inset-0 flex flex-col justify-start p-8 text-white">
              <div class="text-6xl font-bold">300+</div>
              <div class="text-4xl font-bold">Line<br>Icons</div>
            </div>
            <div class="absolute bottom-0 right-0 p-4">
              <div class="grid grid-cols-3 gap-2">
                <img src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0IiBmaWxsPSJub25lIiBzdHJva2U9IiNmZmZmZmYiIHN0cm9rZS13aWR0aD0iMiIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIiBzdHJva2UtbGluZWpvaW49InJvdW5kIj48Y2lyY2xlIGN4PSIxMiIgY3k9IjEyIiByPSIxMCI+PC9jaXJjbGU+PGNpcmNsZSBjeD0iMTIiIGN5PSIxMiIgcj0iNCIgc3Ryb2tlPSIjZmZmZmZmIj48L2NpcmNsZT48L3N2Zz4=" alt="Icon" class="w-6 h-6">
                <img src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0IiBmaWxsPSJub25lIiBzdHJva2U9IiNmZmZmZmYiIHN0cm9rZS13aWR0aD0iMiIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIiBzdHJva2UtbGluZWpvaW49InJvdW5kIj48Y2lyY2xlIGN4PSIxMiIgY3k9IjEyIiByPSIxMCI+PC9jaXJjbGU+PGxpbmUgeDE9IjIiIHkxPSIxMiIgeDI9IjIyIiB5Mj0iMTIiPjwvbGluZT48L3N2Zz4=" alt="Icon" class="w-6 h-6">
                <img src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0IiBmaWxsPSJub25lIiBzdHJva2U9IiNmZmZmZmYiIHN0cm9rZS13aWR0aD0iMiIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIiBzdHJva2UtbGluZWpvaW49InJvdW5kIj48cGF0aCBkPSJNMTIgMjJzOC04IDgtMTRhOCA4IDAgMSAwLTE2IDBjMCA2IDggMTQgOCAxNHoiPjwvcGF0aD48Y2lyY2xlIGN4PSIxMiIgY3k9IjgiIHI9IjQiPjwvY2lyY2xlPjwvc3ZnPg==" alt="Icon" class="w-6 h-6">
              </div>
              <div class="grid grid-cols-3 gap-2 mt-2">
                <img src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0IiBmaWxsPSJub25lIiBzdHJva2U9IiNmZmZmZmYiIHN0cm9rZS13aWR0aD0iMiIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIiBzdHJva2UtbGluZWpvaW49InJvdW5kIj48cGF0aCBkPSJNMTcgMjFsLTcuNS03LjUgNy41LTcuNSI+PC9wYXRoPjwvc3ZnPg==" alt="Icon" class="w-6 h-6">
                <img src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0IiBmaWxsPSJub25lIiBzdHJva2U9IiNmZmZmZmYiIHN0cm9rZS13aWR0aD0iMiIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIiBzdHJva2UtbGluZWpvaW49InJvdW5kIj48cGF0aCBkPSJNMTIgMTlsLTctNyA3LTciPjwvcGF0aD48cGF0aCBkPSJNMTkgMTJINSI+PC9wYXRoPjwvc3ZnPg==" alt="Icon" class="w-6 h-6">
                <img src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0IiBmaWxsPSJub25lIiBzdHJva2U9IiNmZmZmZmYiIHN0cm9rZS13aWR0aD0iMiIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIiBzdHJva2UtbGluZWpvaW49InJvdW5kIj48cGF0aCBkPSJNMTggOGE2IDYgMCAwIDAtOS4zMyA1aDEwLjQ0QTYgNiAwIDAgMCAxOCA4eiI+PC9wYXRoPjxsaW5lIHgxPSIxIiB5MT0iMTMiIHgyPSIyMyIgeTI9IjEzIj48L2xpbmU+PHBhdGggZD0iTTguNTkgMTMuNTFsNS40MSA3Ljk1IDUuNDEtNy45NUg4LjU5eiI+PC9wYXRoPjwvc3ZnPg==" alt="Icon" class="w-6 h-6">
              </div>
            </div>
          </div>
          <div class="p-4">
            <h3 class="font-medium text-gray-900">300+ Business Line Icons Pack</h3>
            <p class="text-gray-500 text-sm">Icons</p>
            <p class="text-gray-900 font-medium mt-2">$20.00</p>
          </div>
        </div>
        
        <!-- Product Card 2 -->
        <div class="bg-white rounded-lg overflow-hidden shadow-sm hover:shadow-md transition-shadow">
          <div class="relative bg-[#1a2b47] aspect-square">
            <div class="absolute inset-0 flex flex-col justify-start p-6 text-white">
              <p class="text-sm mb-2">universal icons for</p>
              <h3 class="text-3xl font-bold mb-4">Web & Mobile</h3>
              <div class="grid grid-cols-5 gap-2">
                <img src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0IiBmaWxsPSJub25lIiBzdHJva2U9IiNmZmZmZmYiIHN0cm9rZS13aWR0aD0iMiIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIiBzdHJva2UtbGluZWpvaW49InJvdW5kIj48Y2lyY2xlIGN4PSIxMSIgY3k9IjExIiByPSI4Ij48L2NpcmNsZT48bGluZSB4MT0iMjEiIHkxPSIyMSIgeDI9IjE2LjY1IiB5Mj0iMTYuNjUiPjwvbGluZT48L3N2Zz4=" alt="Icon" class="w-5 h-5">
                <img src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0IiBmaWxsPSJub25lIiBzdHJva2U9IiNmZmZmZmYiIHN0cm9rZS13aWR0aD0iMiIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIiBzdHJva2UtbGluZWpvaW49InJvdW5kIj48cGF0aCBkPSJNMTEgNEg0YTIgMiAwIDAgMC0yIDJ2MTRhMiAyIDAgMCAwIDIgMmgxNGEyIDIgMCAwIDAgMi0ydi03Ij48L3BhdGg+PHBhdGggZD0iTTE4LjUgMi41YTIuMTIxIDIuMTIxIDAgMCAxIDMgM0wxMiAxNWwtNCAxIDEtNEwyMS41IDIuNXoiPjwvcGF0aD48L3N2Zz4=" alt="Icon" class="w-5 h-5">
                <img src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0IiBmaWxsPSJub25lIiBzdHJva2U9IiNmZmZmZmYiIHN0cm9rZS13aWR0aD0iMiIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIiBzdHJva2UtbGluZWpvaW49InJvdW5kIj48cGF0aCBkPSJNMTQgMkg2YTIgMiAwIDAgMC0yIDJ2MTZhMiAyIDAgMCAwIDIgMmgxMmEyIDIgMCAwIDAgMi0yVjh6Ij48L3BhdGg+PHBvbHlsaW5lIHBvaW50cz0iMTQgMiAxNCA4IDIwIDgiPjwvcG9seWxpbmU+PC9zdmc+" alt="Icon" class="w-5 h-5">
                <img src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0IiBmaWxsPSJub25lIiBzdHJva2U9IiNmZmZmZmYiIHN0cm9rZS13aWR0aD0iMiIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIiBzdHJva2UtbGluZWpvaW49InJvdW5kIj48cGF0aCBkPSJNMTIgMjJzOC04IDgtMTRhOCA4IDAgMSAwLTE2IDBjMCA2IDggMTQgOCAxNHoiPjwvcGF0aD48Y2lyY2xlIGN4PSIxMiIgY3k9IjgiIHI9IjQiPjwvY2lyY2xlPjwvc3ZnPg==" alt="Icon" class="w-5 h-5">
                <img src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0IiBmaWxsPSJub25lIiBzdHJva2U9IiNmZmZmZmYiIHN0cm9rZS13aWR0aD0iMiIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIiBzdHJva2UtbGluZWpvaW49InJvdW5kIj48Y2lyY2xlIGN4PSIxMiIgY3k9IjEyIiByPSIxMCI+PC9jaXJjbGU+PHBvbHlnb24gcG9pbnRzPSIxNi4yNCAxNC4zNCAxMy43NiAxMi4zNiAxMy43NiA1LjUgMTAuMjQgNS41IDEwLjI0IDEyLjM2IDcuNzYgMTQuMzQiPjwvcG9seWdvbj48bGluZSB4MT0iNy41OSIgeTE9IjE4LjUiIHgyPSIxNi40MSIgeTI9IjE4LjUiPjwvbGluZT48L3N2Zz4=" alt="Icon" class="w-5 h-5">
              </div>
              <div class="grid grid-cols-5 gap-2 mt-2">
                <img src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0IiBmaWxsPSJub25lIiBzdHJva2U9IiNmZmZmZmYiIHN0cm9rZS13aWR0aD0iMiIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIiBzdHJva2UtbGluZWpvaW49InJvdW5kIj48cGF0aCBkPSJNMjIgMTlhMiAyIDAgMCAxLTIgMkg0YTIgMiAwIDAgMS0yLTJWNWEyIDIgMCAwIDEgMi0yaDVsMiAyaDlhMiAyIDAgMCAxIDIgMnoiPjwvcGF0aD48L3N2Zz4=" alt="Icon" class="w-5 h-5">
                <img src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0IiBmaWxsPSJub25lIiBzdHJva2U9IiNmZmZmZmYiIHN0cm9rZS13aWR0aD0iMiIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIiBzdHJva2UtbGluZWpvaW49InJvdW5kIj48cGF0aCBkPSJNMTggMTVoLTZhMyAzIDAgMCAwLTMgM3YzaDEydi0zYTMgMyAwIDAgMC0zLTN6Ij48L3BhdGg+PGNpcmNsZSBjeD0iMTUiIGN5PSI3IiByPSI0Ij48L2NpcmNsZT48L3N2Zz4=" alt="Icon" class="w-5 h-5">
                <img src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0IiBmaWxsPSJub25lIiBzdHJva2U9IiNmZmZmZmYiIHN0cm9rZS13aWR0aD0iMiIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIiBzdHJva2UtbGluZWpvaW49InJvdW5kIj48cGF0aCBkPSJNMjAgMjFWNWEyIDIgMCAwIDAtMi0yaC0xMGEyIDIgMCAwIDAtMiAydjE2Ij48L3BhdGg+PHBhdGggZD0iTTIgMTBoMjAiPjwvcGF0aD48L3N2Zz4=" alt="Icon" class="w-5 h-5">
                <img src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0IiBmaWxsPSJub25lIiBzdHJva2U9IiNmZmZmZmYiIHN0cm9rZS13aWR0aD0iMiIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIiBzdHJva2UtbGluZWpvaW49InJvdW5kIj48cGF0aCBkPSJNMTIgMTljMy44NyAwIDcgLTMuMTMgNyAtN3YtMmMwIC0yLjc2IC0yLjI0IC01IC01IC01YTUgNSAwIDAgMCAtNSA1djJoLTNtNCA0YTIgMiAwIDEgMCAwIC00YTIgMiAwIDAgMCAwIDR6Ij48L3BhdGg+PC9zdmc+" alt="Icon" class="w-5 h-5">
                <img src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0IiBmaWxsPSJub25lIiBzdHJva2U9IiNmZmZmZmYiIHN0cm9rZS13aWR0aD0iMiIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIiBzdHJva2UtbGluZWpvaW49InJvdW5kIj48cGF0aCBkPSJNMTIgMTljMy44NyAwIDcgLTMuMTMgNyAtN3YtMmMwIC0yLjc2IC0yLjI0IC01IC01IC01YTUgNSAwIDAgMCAtNSA1djJoLTNtNCA0YTIgMiAwIDEgMCAwIC00YTIgMiAwIDAgMCAwIDR6Ij48L3BhdGg+PC9zdmc+" alt="Icon" class="w-5 h-5">
              </div>
              <div class="grid grid-cols-5 gap-2 mt-2">
                <img src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0IiBmaWxsPSJub25lIiBzdHJva2U9IiNmZmZmZmYiIHN0cm9rZS13aWR0aD0iMiIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIiBzdHJva2UtbGluZWpvaW49InJvdW5kIj48cGF0aCBkPSJNMTIgMTljMy44NyAwIDcgLTMuMTMgNyAtN3YtMmMwIC0yLjc2IC0yLjI0IC01IC01IC01YTUgNSAwIDAgMCAtNSA1djJoLTNtNCA0YTIgMiAwIDEgMCAwIC00YTIgMiAwIDAgMCAwIDR6Ij48L3BhdGg+PC9zdmc+" alt="Icon" class="w-5 h-5">
                <img src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0IiBmaWxsPSJub25lIiBzdHJva2U9IiNmZmZmZmYiIHN0cm9rZS13aWR0aD0iMiIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIiBzdHJva2UtbGluZWpvaW49InJvdW5kIj48cGF0aCBkPSJNMTIgMTljMy44NyAwIDcgLTMuMTMgNyAtN3YtMmMwIC0yLjc2IC0yLjI0IC01IC01IC01YTUgNSAwIDAgMCAtNSA1djJoLTNtNCA0YTIgMiAwIDEgMCAwIC00YTIgMiAwIDAgMCAwIDR6Ij48L3BhdGg+PC9zdmc+" alt="Icon" class="w-5 h-5">
                <img src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0IiBmaWxsPSJub25lIiBzdHJva2U9IiNmZmZmZmYiIHN0cm9rZS13aWR0aD0iMiIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIiBzdHJva2UtbGluZWpvaW49InJvdW5kIj48cGF0aCBkPSJNMTIgMTljMy44NyAwIDcgLTMuMTMgNyAtN3YtMmMwIC0yLjc2IC0yLjI0IC01IC01IC01YTUgNSAwIDAgMCAtNSA1djJoLTNtNCA0YTIgMiAwIDEgMCAwIC00YTIgMiAwIDAgMCAwIDR6Ij48L3BhdGg+PC9zdmc+" alt="Icon" class="w-5 h-5">
                <img src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0IiBmaWxsPSJub25lIiBzdHJva2U9IiNmZmZmZmYiIHN0cm9rZS13aWR0aD0iMiIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIiBzdHJva2UtbGluZWpvaW49InJvdW5kIj48cGF0aCBkPSJNMTIgMTljMy44NyAwIDcgLTMuMTMgNyAtN3YtMmMwIC0yLjc2IC0yLjI0IC01IC01IC01YTUgNSAwIDAgMCAtNSA1djJoLTNtNCA0YTIgMiAwIDEgMCAwIC00YTIgMiAwIDAgMCAwIDR6Ij48L3BhdGg+PC9zdmc+" alt="Icon" class="w-5 h-5">
                <img src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0IiBmaWxsPSJub25lIiBzdHJva2U9IiNmZmZmZmYiIHN0cm9rZS13aWR0aD0iMiIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIiBzdHJva2UtbGluZWpvaW49InJvdW5kIj48cGF0aCBkPSJNMTIgMTljMy44NyAwIDcgLTMuMTMgNyAtN3YtMmMwIC0yLjc2IC0yLjI0IC01IC01IC01YTUgNSAwIDAgMCAtNSA1djJoLTNtNCA0YTIgMiAwIDEgMCAwIC00YTIgMiAwIDAgMCAwIDR6Ij48L3BhdGg+PC9zdmc+" alt="Icon" class="w-5 h-5">
              </div>
            </div>
            <div class="absolute bottom-0 w-full flex justify-center">
              <div class="w-2 h-2 bg-white rounded-full mx-1"></div>
            </div>
          </div>
          <div class="p-4">
            <h3 class="font-medium text-gray-900">Universal Icons - 1000+ Licensed Vector Files</h3>
            <p class="text-gray-500 text-sm">Icons</p>
            <p class="text-gray-900 font-medium mt-2">$22.00</p>
          </div>
        </div>
        
        <!-- Product Card 3 -->
        <div class="bg-white rounded-lg overflow-hidden shadow-sm hover:shadow-md transition-shadow">
          <div class="relative bg-[#1a2b47] aspect-square">
            <div class="absolute inset-0 flex flex-col justify-between">
              <div class="p-6">
                <h3 class="text-3xl font-bold text-white">Agency Template</h3>
                <p class="text-gray-300 text-sm">multi-color premium design</p>
              </div>
              <div class="w-full">
                <img src="data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iNDAwIiBoZWlnaHQ9IjIwMCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj48cmVjdCB3aWR0aD0iNDAwIiBoZWlnaHQ9IjIwMCIgZmlsbD0iIzFhMmI0NyIvPjxyZWN0IHg9IjUwIiB5PSI1MCIgd2lkdGg9IjMwMCIgaGVpZ2h0PSIxMDAiIGZpbGw9IiMxMTFiMmUiIHJ4PSI1IiByeT0iNSIvPjx0ZXh0IHg9IjgwIiB5PSI5MCIgZm9udC1mYW1pbHk9IkFyaWFsIiBmb250LXNpemU9IjE0IiBmaWxsPSJ3aGl0ZSI+VGhlIGJlc3Qgd2F5PC90ZXh0Pjx0ZXh0IHg9IjgwIiB5PSIxMTAiIGZvbnQtZmFtaWx5PSJBcmlhbCIgZm9udC1zaXplPSIxNCIgZmlsbD0id2hpdGUiPnRvIGNyZWF0ZTwvdGV4dD48dGV4dCB4PSI4MCIgeT0iMTMwIiBmb250LWZhbWlseT0iQXJpYWwiIGZvbnQtc2l6ZT0iMTQiIGZpbGw9IndoaXRlIj55b3VyIG93biBhcHBzLjwvdGV4dD48Y2lyY2xlIGN4PSIzMDAiIGN5PSIxMDAiIHI9IjIwIiBmaWxsPSIjODgzM2ZmIi8+PGNpcmNsZSBjeD0iMzQwIiBjeT0iNzAiIHI9IjEwIiBmaWxsPSIjZmY1NTMzIi8+PHJlY3QgeD0iODAiIHk9IjE1MCIgd2lkdGg9IjUwIiBoZWlnaHQ9IjIwIiBmaWxsPSIjMzM2NmZmIiByeD0iNSIgcnk9IjUiLz48dGV4dCB4PSI5MCIgeT0iMTY1IiBmb250LWZhbWlseT0iQXJpYWwiIGZvbnQtc2l6ZT0iMTAiIGZpbGw9IndoaXRlIj5CdXk8L3RleHQ+PC9zdmc+" alt="Agency Template Preview" class="w-full">
              </div>
              <div class="absolute bottom-0 w-full flex justify-center pb-2">
                <div class="w-2 h-2 bg-white rounded-full mx-1"></div>
                <div class="w-2 h-2 bg-gray-400 rounded-full mx-1"></div>
              </div>
            </div>
          </div>
          <div class="p-4">
            <h3 class="font-medium text-gray-900">Professional Digital Agency Website Template</h3>
            <p class="text-gray-500 text-sm">UI Kits</p>
            <p class="text-gray-900 font-medium mt-2">$55.00</p>
          </div>
        </div>
        
        <!-- Product Card 4 -->
        <div class="bg-white rounded-lg overflow-hidden shadow-sm hover:shadow-md transition-shadow">
          <div class="relative bg-[#3b5998] aspect-square">
            <div class="absolute inset-0 flex flex-col justify-between">
              <div class="p-6">
                <h3 class="text-5xl font-bold text-white">Translate</h3>
                <p class="text-gray-300 text-sm mt-2">clean language ui</p>
              </div>
              <div class="w-full flex justify-center pb-6">
                <img src="data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMzAwIiBoZWlnaHQ9IjIwMCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj48cmVjdCB3aWR0aD0iMzAwIiBoZWlnaHQ9IjIwMCIgZmlsbD0iIzNiNTk5OCIgb3BhY2l0eT0iMCIvPjxnIHRyYW5zZm9ybT0idHJhbnNsYXRlKDUwLCA0MCkiPjxyZWN0IHg9IjAiIHk9IjAiIHdpZHRoPSI2MCIgaGVpZ2h0PSIxMjAiIGZpbGw9IiNmZmZmZmYiIHJ4PSIxMCIgcnk9IjEwIi8+PHJlY3QgeD0iNzAiIHk9IjAiIHdpZHRoPSI2MCIgaGVpZ2h0PSIxMjAiIGZpbGw9IiNmZmZmZmYiIHJ4PSIxMCIgcnk9IjEwIi8+PHJlY3QgeD0iMTQwIiB5PSIwIiB3aWR0aD0iNjAiIGhlaWdodD0iMTIwIiBmaWxsPSIjZmZmZmZmIiByeD0iMTAiIHJ5PSIxMCIvPjx0ZXh0IHg9IjEwIiB5PSIzMCIgZm9udC1mYW1pbHk9IkFyaWFsIiBmb250LXNpemU9IjEyIiBmaWxsPSIjMzMzIj5IRUxMTyA5PC90ZXh0Pjx0ZXh0IHg9IjgwIiB5PSIzMCIgZm9udC1mYW1pbHk9IkFyaWFsIiBmb250LXNpemU9IjEyIiBmaWxsPSIjMzMzIj5JVEFMWTwvdGV4dD48dGV4dCB4PSIxNTAiIHk9IjMwIiBmb250LWZhbWlseT0iQXJpYWwiIGZvbnQtc2l6ZT0iMTAiIGZpbGw9IiMzMzMiPlRyYW5zbGF0ZSB0aGVzZTwvdGV4dD48dGV4dCB4PSIxNTAiIHk9IjQ1IiBmb250LWZhbWlseT0iQXJpYWwiIGZvbnQtc2l6ZT0iMTAiIGZpbGw9IiMzMzMiPnBocmFzZSB0byBFbmdsaXNoPC90ZXh0PjxjaXJjbGUgY3g9IjIwIiBjeT0iNjAiIHI9IjEwIiBmaWxsPSIjZmZjYzAwIi8+PGNpcmNsZSBjeD0iODAiIGN5PSI2MCIgcj0iMTAiIGZpbGw9IiMwMGNjZmYiLz48Y2lyY2xlIGN4PSIxNTAiIGN5PSI2MCIgcj0iMTAiIGZpbGw9IiNmZjY2MDAiLz48L2c+PC9zdmc+" alt="TranslateUI Preview" class="h-32">
              </div>
            </div>
          </div>
          <div class="p-4">
            <h3 class="font-medium text-gray-900">TranslateUI - Premium Translation App Design Toolkit</h3>
            <p class="text-gray-500 text-sm">UI Kits</p>
            <p class="text-gray-900 font-medium mt-2">$9.99</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Navbar from './components/Navbar.vue'
import ProductDetail from './components/ProductDetail.vue'

export default {
  name: 'App',
  components: {
    Navbar,
    ProductDetail
  }
}
</script>

<style>
@keyframes float {
  0% {
    transform: translateY(0px);
  }
  50% {
    transform: translateY(-20px);
  }
  100% {
    transform: translateY(0px);
  }
}

@keyframes float-slow {
  0% {
    transform: translateY(0px) translateX(0px);
  }
  25% {
    transform: translateY(-10px) translateX(10px);
  }
  50% {
    transform: translateY(5px) translateX(15px);
  }
  75% {
    transform: translateY(10px) translateX(-5px);
  }
  100% {
    transform: translateY(0px) translateX(0px);
  }
}

@keyframes float-product {
  0% {
    transform: translateY(0px) translateX(0px) rotate(0deg);
  }
  25% {
    transform: translateY(-15px) translateX(10px) rotate(2deg);
  }
  50% {
    transform: translateY(5px) translateX(15px) rotate(-1deg);
  }
  75% {
    transform: translateY(10px) translateX(-10px) rotate(1deg);
  }
  100% {
    transform: translateY(0px) translateX(0px) rotate(0deg);
  }
}

@keyframes float-rotate {
  0% {
    transform: translateY(0px) rotate(0deg);
  }
  50% {
    transform: translateY(-15px) rotate(10deg);
  }
  100% {
    transform: translateY(0px) rotate(0deg);
  }
}

@keyframes animate-gradient {
  0% {
    background-position: 0% 50%;
  }
  50% {
    background-position: 100% 50%;
  }
  100% {
    background-position: 0% 50%;
  }
}

@keyframes slow-spin {
  from {
    transform: translate(-50%, -50%) rotate(0deg);
  }
  to {
    transform: translate(-50%, -50%) rotate(360deg);
  }
}

@keyframes slow-spin-reverse {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(-360deg);
  }
}

.animate-slow-spin {
  animation: slow-spin 60s linear infinite;
}

.animate-slow-spin-reverse {
  animation: slow-spin-reverse 45s linear infinite;
}

.animate-float-slow {
  animation: float-slow 20s ease-in-out infinite;
}

.animate-float-product {
  animation: float-product 25s ease-in-out infinite;
}

.animate-float-rotate {
  animation: float-rotate 15s ease-in-out infinite;
}

.animate-gradient {
  background-size: 200% 200%;
  animation: animate-gradient 6s ease infinite;
}

/* Grid Pattern */
.bg-grid-pattern {
  background-image: 
    linear-gradient(to right, rgba(0, 0, 0, 0.05) 1px, transparent 1px),
    linear-gradient(to bottom, rgba(0, 0, 0, 0.05) 1px, transparent 1px);
  background-size: 20px 20px;
}

/* Particle animations */
.particle {
  position: absolute;
  width: 6px;
  height: 6px;
  border-radius: 50%;
  opacity: 0.3;
}

@keyframes particle-1 {
  0%, 100% {
    transform: translate(10vw, 10vh);
  }
  25% {
    transform: translate(30vw, 40vh);
  }
  50% {
    transform: translate(70vw, 30vh);
  }
  75% {
    transform: translate(50vw, 60vh);
  }
}

@keyframes particle-2 {
  0%, 100% {
    transform: translate(80vw, 20vh);
  }
  25% {
    transform: translate(20vw, 30vh);
  }
  50% {
    transform: translate(40vw, 70vh);
  }
  75% {
    transform: translate(60vw, 40vh);
  }
}

@keyframes particle-3 {
  0%, 100% {
    transform: translate(30vw, 80vh);
  }
  25% {
    transform: translate(70vw, 50vh);
  }
  50% {
    transform: translate(20vw, 30vh);
  }
  75% {
    transform: translate(80vw, 20vh);
  }
}

@keyframes particle-4 {
  0%, 100% {
    transform: translate(60vw, 10vh);
  }
  25% {
    transform: translate(40vw, 30vh);
  }
  50% {
    transform: translate(10vw, 50vh);
  }
  75% {
    transform: translate(50vw, 70vh);
  }
}

@keyframes particle-5 {
  0%, 100% {
    transform: translate(50vw, 50vh);
  }
  25% {
    transform: translate(20vw, 70vh);
  }
  50% {
    transform: translate(80vw, 30vh);
  }
  75% {
    transform: translate(40vw, 10vh);
  }
}

.animate-particle-1 {
  animation: particle-1 30s ease-in-out infinite;
}

.animate-particle-2 {
  animation: particle-2 35s ease-in-out infinite;
}

.animate-particle-3 {
  animation: particle-3 40s ease-in-out infinite;
}

.animate-particle-4 {
  animation: particle-4 45s ease-in-out infinite;
}

.animate-particle-5 {
  animation: particle-5 50s ease-in-out infinite;
}
</style>
