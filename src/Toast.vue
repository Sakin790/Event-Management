<template>
    <div class="fixed bottom-4 right-4 z-50 flex items-center w-full max-w-xs p-4 mb-4 text-gray-500 bg-white rounded-lg shadow-lg dark:text-gray-400 dark:bg-gray-800"
        role="alert">
        <div
            class="inline-flex items-center justify-center flex-shrink-0 w-8 h-8 text-blue-500 bg-blue-100 rounded-lg dark:bg-blue-800 dark:text-blue-200">
            <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg">
                <path fill-rule="evenodd"
                    d="M18 13a1 1 0 01-.707 1.707L10 14l-7.293 1.707A1 1 0 011 14V6a1 1 0 01.293-.707l7.293-7.293a1 1 0 011.414 0l7.293 7.293A1 1 0 0118 6v7zm-6-3a1 1 0 01-.293.707L10 13.414l-1.707 1.707A1 1 0 017 14v-3a1 1 0 01.293-.707L10 8.586l1.707-1.707A1 1 0 0113 8v2zm-6-1a1 1 0 01-.293.707L4 10.414l-1.707 1.707A1 1 0 011 10V6a1 1 0 01.293-.707L4 4.586l1.707-1.707A1 1 0 016 4v2zm6 4a1 1 0 01-.293.707L10 14.414l-1.707 1.707A1 1 0 017 14v-4a1 1 0 01.293-.707L10 7.586l1.707-1.707A1 1 0 0113 8v5z"
                    clip-rule="evenodd"></path>
            </svg>
        </div>
        <div class="ml-3 text-sm font-normal">This is a toast message.</div>
        <button type="button"
            class="ml-auto -mx-1.5 -my-1.5 bg-white text-gray-400 rounded-lg focus:ring-2 focus:ring-gray-300 p-1.5 hover:bg-gray-100 inline-flex h-8 w-8 dark:bg-gray-800 dark:text-gray-500 dark:hover:bg-gray-700"
            data-dismiss-target="#toast-default" aria-label="Close">
            <span class="sr-only">Close</span>
            <svg aria-hidden="true" class="w-5 h-5" fill="currentColor" viewBox="0 0 20 20"
                xmlns="http://www.w3.org/2000/svg">
                <path fill-rule="evenodd"
                    d="M4.293 4.293a1 1 0 011.414 0L10 8.586l4.293-4.293a1 1 0 011.414 1.414L11.414 10l4.293 4.293a1 1 0 01-1.414 1.414L10 11.414l-4.293 4.293a1 1 0 01-1.414-1.414L8.586 10 4.293 5.707a1 1 0 010-1.414z"
                    clip-rule="evenodd"></path>
            </svg>
        </button>
    </div>

</template>