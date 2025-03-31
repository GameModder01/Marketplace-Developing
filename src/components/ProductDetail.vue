<template>
  <div class="bg-white">
    <!-- Breadcrumb -->
    <div class="container mx-auto px-6 py-4">
      <div class="flex items-center text-sm text-gray-500">
        <a href="#" class="hover:text-blue-500 transition-colors">Home</a>
        <span class="mx-2">/</span>
        <a href="#" class="hover:text-blue-500 transition-colors">Products</a>
      </div>
    </div>

    <div class="container mx-auto px-6 pb-12">
      <!-- Auf Desktop: Produktinfo links, Bildergalerie rechts -->
      <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 lg:flex lg:flex-row-reverse">
        <!-- Image Gallery -->
        <div class="relative lg:w-1/2">
          <!-- Main Image -->
          <div class="relative rounded-xl overflow-hidden bg-gray-100 aspect-[4/3] group">
            <img 
              :src="images[currentImageIndex].src" 
              :alt="images[currentImageIndex].alt" 
              class="w-full h-full object-cover transition-opacity duration-500"
            />
            
            <!-- Nur rechter Navigationspfeil, der bei Hover erscheint -->
            <button 
              @click="nextImage" 
              class="absolute right-4 top-1/2 transform -translate-y-1/2 bg-white rounded-full p-2 shadow-md hover:bg-gray-100 transition-colors focus:outline-none opacity-0 group-hover:opacity-100 transition-opacity duration-300"
              aria-label="Next image"
            >
              <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-gray-700" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7" />
              </svg>
            </button>
          </div>
          
          <!-- Image Counter -->
          <div class="absolute top-4 right-4 bg-black/50 text-white text-xs px-2 py-1 rounded-md">
            {{ currentImageIndex + 1 }} / {{ images.length }}
          </div>
        </div>
        
        <!-- Product Info -->
        <div class="lg:w-1/2">
          <h1 class="text-3xl font-bold text-gray-900 mb-2">Professional Digital Agency Website Template</h1>
          <div class="text-sm text-gray-500 mb-4">UI Kits</div>
          
          <div class="text-2xl font-bold text-gray-900 mb-6">$55.00</div>
          
          <div class="flex items-center text-green-600 mb-6">
            <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 mr-2" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
            </svg>
            <span>Eligible for instant delivery</span>
          </div>
          
          <button class="w-full bg-blue-500 hover:bg-blue-600 text-white font-medium py-3 px-6 rounded-lg transition-colors mb-6">
            Add to cart
          </button>
          
          <div class="flex items-center justify-center text-gray-500 mb-8">
            <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 mr-2" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4.318 6.318a4.5 4.5 0 000 6.364L12 20.364l7.682-7.682a4.5 4.5 0 00-6.364-6.364L12 7.636l-1.318-1.318a4.5 4.5 0 00-6.364 0z" />
            </svg>
            <span>30 Day Return Guarantee</span>
          </div>
          
          <!-- Product Description -->
          <div class="border-t border-gray-200 pt-6">
            <h2 class="text-lg font-medium text-gray-900 mb-4">Description</h2>
            <div class="prose text-gray-600">
              <p class="mb-4">
                A premium website template designed specifically for digital agencies and creative studios. This template includes everything you need to showcase your services and portfolio in a professional way.
              </p>
              <ul class="list-disc pl-5 mb-4">
                <li>Responsive design for all devices</li>
                <li>Modern and clean UI components</li>
                <li>Easy to customize with Tailwind CSS</li>
                <li>Optimized for performance</li>
                <li>Cross-browser compatibility</li>
              </ul>
              <p>
                Perfect for agencies looking to establish a strong online presence with a sleek, professional website.
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ProductDetail',
  data() {
    return {
      currentImageIndex: 0,
      images: [
        {
          src: "data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iODAwIiBoZWlnaHQ9IjYwMCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj48cmVjdCB3aWR0aD0iODAwIiBoZWlnaHQ9IjYwMCIgZmlsbD0iIzFhMmI0NyIvPjxyZWN0IHg9IjE1MCIgeT0iMTUwIiB3aWR0aD0iNTAwIiBoZWlnaHQ9IjMwMCIgZmlsbD0iIzExMWIyZSIgcng9IjEwIiByeT0iMTAiLz48dGV4dCB4PSIyMDAiIHk9IjIyMCIgZm9udC1mYW1pbHk9IkFyaWFsIiBmb250LXNpemU9IjI0IiBmaWxsPSJ3aGl0ZSI+VGhlIGJlc3Qgd2F5PC90ZXh0Pjx0ZXh0IHg9IjIwMCIgeT0iMjYwIiBmb250LWZhbWlseT0iQXJpYWwiIGZvbnQtc2l6ZT0iMjQiIGZpbGw9IndoaXRlIj50byBjcmVhdGU8L3RleHQ+PHRleHQgeD0iMjAwIiB5PSIzMDAiIGZvbnQtZmFtaWx5PSJBcmlhbCIgZm9udC1zaXplPSIyNCIgZmlsbD0id2hpdGUiPnlvdXIgb3duIGFwcHMuPC90ZXh0PjxjaXJjbGUgY3g9IjYwMCIgY3k9IjIwMCIgcj0iMzAiIGZpbGw9IiM4ODMzZmYiLz48Y2lyY2xlIGN4PSI2NTAiIGN5PSIxNzAiIHI9IjE1IiBmaWxsPSIjZmY1NTMzIi8+PHJlY3QgeD0iMjAwIiB5PSIzNTAiIHdpZHRoPSIxMDAiIGhlaWdodD0iNDAiIGZpbGw9IiMzMzY2ZmYiIHJ4PSI1IiByeT0iNSIvPjx0ZXh0IHg9IjIyMCIgeT0iMzc1IiBmb250LWZhbWlseT0iQXJpYWwiIGZvbnQtc2l6ZT0iMTYiIGZpbGw9IndoaXRlIj5UcnkgaXQgZnJlZTwvdGV4dD48L3N2Zz4=",
          alt: "Agency Template - Main View"
        },
        {
          src: "data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iODAwIiBoZWlnaHQ9IjYwMCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj48cmVjdCB3aWR0aD0iODAwIiBoZWlnaHQ9IjYwMCIgZmlsbD0iIzFhMmI0NyIvPjxyZWN0IHg9IjUwIiB5PSI1MCIgd2lkdGg9IjcwMCIgaGVpZ2h0PSI4MCIgZmlsbD0iIzExMWIyZSIgcng9IjUiIHJ5PSI1Ii8+PHRleHQgeD0iMTAwIiB5PSI5NSIgZm9udC1mYW1pbHk9IkFyaWFsIiBmb250LXNpemU9IjI0IiBmaWxsPSJ3aGl0ZSI+QWJvdXQgVXM8L3RleHQ+PHJlY3QgeD0iNTAiIHk9IjE1MCIgd2lkdGg9IjM0MCIgaGVpZ2h0PSI0MDAiIGZpbGw9IiMxMTFiMmUiIHJ4PSI1IiByeT0iNSIvPjx0ZXh0IHg9IjgwIiB5PSIyMDAiIGZvbnQtZmFtaWx5PSJBcmlhbCIgZm9udC1zaXplPSIyMCIgZmlsbD0id2hpdGUiPldlIGFyZSBhIGRpZ2l0YWwgYWdlbmN5PC90ZXh0Pjx0ZXh0IHg9IjgwIiB5PSIyNDAiIGZvbnQtZmFtaWx5PSJBcmlhbCIgZm9udC1zaXplPSIyMCIgZmlsbD0id2hpdGUiPnNwZWNpYWxpemluZyBpbiBjcmVhdGluZzwvdGV4dD48dGV4dCB4PSI4MCIgeT0iMjgwIiBmb250LWZhbWlseT0iQXJpYWwiIGZvbnQtc2l6ZT0iMjAiIGZpbGw9IndoaXRlIj5iZWF1dGlmdWwgZGlnaXRhbCBleHBlcmllbmNlcy48L3RleHQ+PHJlY3QgeD0iNDEwIiB5PSIxNTAiIHdpZHRoPSIzNDAiIGhlaWdodD0iNDAwIiBmaWxsPSIjMzM2NmZmIiByeD0iNSIgcnk9IjUiLz48Y2lyY2xlIGN4PSI1ODAiIGN5PSIzNTAiIHI9IjEwMCIgZmlsbD0iIzg4MzNmZiIvPjwvc3ZnPg==",
          alt: "Agency Template - About Page"
        },
        {
          src: "data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iODAwIiBoZWlnaHQ9IjYwMCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj48cmVjdCB3aWR0aD0iODAwIiBoZWlnaHQ9IjYwMCIgZmlsbD0iIzFhMmI0NyIvPjxyZWN0IHg9IjUwIiB5PSI1MCIgd2lkdGg9IjcwMCIgaGVpZ2h0PSI4MCIgZmlsbD0iIzExMWIyZSIgcng9IjUiIHJ5PSI1Ii8+PHRleHQgeD0iMTAwIiB5PSI5NSIgZm9udC1mYW1pbHk9IkFyaWFsIiBmb250LXNpemU9IjI0IiBmaWxsPSJ3aGl0ZSI+U2VydmljZXM8L3RleHQ+PHJlY3QgeD0iNTAiIHk9IjE1MCIgd2lkdGg9IjIyMCIgaGVpZ2h0PSIyMDAiIGZpbGw9IiMxMTFiMmUiIHJ4PSI1IiByeT0iNSIvPjx0ZXh0IHg9IjgwIiB5PSIyMDAiIGZvbnQtZmFtaWx5PSJBcmlhbCIgZm9udC1zaXplPSIyMCIgZmlsbD0id2hpdGUiPldlYiBEZXNpZ248L3RleHQ+PHJlY3QgeD0iMjkwIiB5PSIxNTAiIHdpZHRoPSIyMjAiIGhlaWdodD0iMjAwIiBmaWxsPSIjMTExYjJlIiByeD0iNSIgcnk9IjUiLz48dGV4dCB4PSIzMjAiIHk9IjIwMCIgZm9udC1mYW1pbHk9IkFyaWFsIiBmb250LXNpemU9IjIwIiBmaWxsPSJ3aGl0ZSI+TW9iaWxlIEFwcHM8L3RleHQ+PHJlY3QgeD0iNTMwIiB5PSIxNTAiIHdpZHRoPSIyMjAiIGhlaWdodD0iMjAwIiBmaWxsPSIjMTExYjJlIiByeD0iNSIgcnk9IjUiLz48dGV4dCB4PSI1NjAiIHk9IjIwMCIgZm9udC1mYW1pbHk9IkFyaWFsIiBmb250LXNpemU9IjIwIiBmaWxsPSJ3aGl0ZSI+QnJhbmRpbmc8L3RleHQ+PHJlY3QgeD0iNTAiIHk9IjM3MCIgd2lkdGg9IjIyMCIgaGVpZ2h0PSIyMDAiIGZpbGw9IiMxMTFiMmUiIHJ4PSI1IiByeT0iNSIvPjx0ZXh0IHg9IjgwIiB5PSI0MjAiIGZvbnQtZmFtaWx5PSJBcmlhbCIgZm9udC1zaXplPSIyMCIgZmlsbD0id2hpdGUiPlNFTzwvdGV4dD48cmVjdCB4PSIyOTAiIHk9IjM3MCIgd2lkdGg9IjIyMCIgaGVpZ2h0PSIyMDAiIGZpbGw9IiMxMTFiMmUiIHJ4PSI1IiByeT0iNSIvPjx0ZXh0IHg9IjMyMCIgeT0iNDIwIiBmb250LWZhbWlseT0iQXJpYWwiIGZvbnQtc2l6ZT0iMjAiIGZpbGw9IndoaXRlIj5Db250ZW50PC90ZXh0PjxyZWN0IHg9IjUzMCIgeT0iMzcwIiB3aWR0aD0iMjIwIiBoZWlnaHQ9IjIwMCIgZmlsbD0iIzExMWIyZSIgcng9IjUiIHJ5PSI1Ii8+PHRleHQgeD0iNTYwIiB5PSI0MjAiIGZvbnQtZmFtaWx5PSJBcmlhbCIgZm9udC1zaXplPSIyMCIgZmlsbD0id2hpdGUiPkFuYWx5dGljczwvdGV4dD48L3N2Zz4=",
          alt: "Agency Template - Services Page"
        },
        {
          src: "data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iODAwIiBoZWlnaHQ9IjYwMCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj48cmVjdCB3aWR0aD0iODAwIiBoZWlnaHQ9IjYwMCIgZmlsbD0iIzFhMmI0NyIvPjxyZWN0IHg9IjUwIiB5PSI1MCIgd2lkdGg9IjcwMCIgaGVpZ2h0PSI4MCIgZmlsbD0iIzExMWIyZSIgcng9IjUiIHJ5PSI1Ii8+PHRleHQgeD0iMTAwIiB5PSI5NSIgZm9udC1mYW1pbHk9IkFyaWFsIiBmb250LXNpemU9IjI0IiBmaWxsPSJ3aGl0ZSI+Q29udGFjdDwvdGV4dD48cmVjdCB4PSI1MCIgeT0iMTUwIiB3aWR0aD0iMzQwIiBoZWlnaHQ9IjQwMCIgZmlsbD0iIzExMWIyZSIgcng9IjUiIHJ5PSI1Ii8+PHRleHQgeD0iODAiIHk9IjIwMCIgZm9udC1mYW1pbHk9IkFyaWFsIiBmb250LXNpemU9IjIwIiBmaWxsPSJ3aGl0ZSI+R2V0IGluIHRvdWNoPC90ZXh0PjxyZWN0IHg9IjgwIiB5PSIyMzAiIHdpZHRoPSIyODAiIGhlaWdodD0iNDAiIGZpbGw9IiMyMjIiIHJ4PSI1IiByeT0iNSIvPjxyZWN0IHg9IjgwIiB5PSIyODAiIHdpZHRoPSIyODAiIGhlaWdodD0iNDAiIGZpbGw9IiMyMjIiIHJ4PSI1IiByeT0iNSIvPjxyZWN0IHg9IjgwIiB5PSIzMzAiIHdpZHRoPSIyODAiIGhlaWdodD0iNDAiIGZpbGw9IiMyMjIiIHJ4PSI1IiByeT0iNSIvPjxyZWN0IHg9IjgwIiB5PSIzODAiIHdpZHRoPSIyODAiIGhlaWdodD0iMTAwIiBmaWxsPSIjMjIyIiByeD0iNSIgcnk9IjUiLz48cmVjdCB4PSI4MCIgeT0iNDkwIiB3aWR0aD0iMTIwIiBoZWlnaHQ9IjQwIiBmaWxsPSIjMzM2NmZmIiByeD0iNSIgcnk9IjUiLz48dGV4dCB4PSIxMDAiIHk9IjUxNSIgZm9udC1mYW1pbHk9IkFyaWFsIiBmb250LXNpemU9IjE2IiBmaWxsPSJ3aGl0ZSI+U3VibWl0PC90ZXh0PjxyZWN0IHg9IjQxMCIgeT0iMTUwIiB3aWR0aD0iMzQwIiBoZWlnaHQ9IjQwMCIgZmlsbD0iIzExMWIyZSIgcng9IjUiIHJ5PSI1Ii8+PHRleHQgeD0iNDQwIiB5PSIyMDAiIGZvbnQtZmFtaWx5PSJBcmlhbCIgZm9udC1zaXplPSIyMCIgZmlsbD0id2hpdGUiPkNvbnRhY3QgSW5mbzwvdGV4dD48dGV4dCB4PSI0NDAiIHk9IjI1MCIgZm9udC1mYW1pbHk9IkFyaWFsIiBmb250LXNpemU9IjE2IiBmaWxsPSJ3aGl0ZSI+aW5mb0BhZ2VuY3kuY29tPC90ZXh0Pjx0ZXh0IHg9IjQ0MCIgeT0iMjkwIiBmb250LWZhbWlseT0iQXJpYWwiIGZvbnQtc2l6ZT0iMTYiIGZpbGw9IndoaXRlIj4rMSAoNTU1KSAxMjMtNDU2NzwvdGV4dD48dGV4dCB4PSI0NDAiIHk9IjMzMCIgZm9udC1mYW1pbHk9IkFyaWFsIiBmb250LXNpemU9IjE2IiBmaWxsPSJ3aGl0ZSI+MTIzIE1haW4gU3RyZWV0PC90ZXh0Pjx0ZXh0IHg9IjQ0MCIgeT0iMzYwIiBmb250LWZhbWlseT0iQXJpYWwiIGZvbnQtc2l6ZT0iMTYiIGZpbGw9IndoaXRlIj5OZXcgWW9yaywgTlkgMTAwMDE8L3RleHQ+PC9zdmc+",
          alt: "Agency Template - Contact Page"
        },
        {
          src: "data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iODAwIiBoZWlnaHQ9IjYwMCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj48cmVjdCB3aWR0aD0iODAwIiBoZWlnaHQ9IjYwMCIgZmlsbD0iIzFhMmI0NyIvPjxyZWN0IHg9IjUwIiB5PSI1MCIgd2lkdGg9IjcwMCIgaGVpZ2h0PSI4MCIgZmlsbD0iIzExMWIyZSIgcng9IjUiIHJ5PSI1Ii8+PHRleHQgeD0iMTAwIiB5PSI5NSIgZm9udC1mYW1pbHk9IkFyaWFsIiBmb250LXNpemU9IjI0IiBmaWxsPSJ3aGl0ZSI+UG9ydGZvbGlvPC90ZXh0PjxyZWN0IHg9IjUwIiB5PSIxNTAiIHdpZHRoPSIyMjAiIGhlaWdodD0iMjAwIiBmaWxsPSIjMzM2NmZmIiByeD0iNSIgcnk9IjUiLz48cmVjdCB4PSIyOTAiIHk9IjE1MCIgd2lkdGg9IjIyMCIgaGVpZ2h0PSIyMDAiIGZpbGw9IiM4ODMzZmYiIHJ4PSI1IiByeT0iNSIvPjxyZWN0IHg9IjUzMCIgeT0iMTUwIiB3aWR0aD0iMjIwIiBoZWlnaHQ9IjIwMCIgZmlsbD0iI2ZmNTUzMyIgcng9IjUiIHJ5PSI1Ii8+PHJlY3QgeD0iNTAiIHk9IjM3MCIgd2lkdGg9IjIyMCIgaGVpZ2h0PSIyMDAiIGZpbGw9IiMzM2NjZmYiIHJ4PSI1IiByeT0iNSIvPjxyZWN0IHg9IjI5MCIgeT0iMzcwIiB3aWR0aD0iMjIwIiBoZWlnaHQ9IjIwMCIgZmlsbD0iIzMzZmY5OSIgcng9IjUiIHJ5PSI1Ii8+PHJlY3QgeD0iNTMwIiB5PSIzNzAiIHdpZHRoPSIyMjAiIGhlaWdodD0iMjAwIiBmaWxsPSIjZmZjYzMzIiByeD0iNSIgcnk9IjUiLz48L3N2Zz4=",
          alt: "Agency Template - Portfolio Page"
        }
      ]
    };
  },
  methods: {
    nextImage() {
      this.currentImageIndex = (this.currentImageIndex + 1) % this.images.length;
    },
    prevImage() {
      this.currentImageIndex = (this.currentImageIndex - 1 + this.images.length) % this.images.length;
    }
  }
};
</script>

<style scoped>
.dropdown-content {
  display: none;
  position: absolute;
  min-width: 160px;
  z-index: 1;
}

.dropdown:hover .dropdown-content {
  display: block;
}
</style>
