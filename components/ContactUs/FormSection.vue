<template>
    <section class="   " id="FormSection">
        <div class="py-8 lg:py-16 px-4 mx-auto max-w-screen-md border my-10 shadow-xl">
            <h2 class="mb-4 text-4xl tracking-tight font-extrabold text-center">Contact Us</h2>
            <p class="mb-8 lg:mb-16 font-light text-center sm:text-xl">Got a technical issue? Want to send feedback about a beta feature? Need details about our Business plan? Let us know.</p>
            <form action="#" class="space-y-8">
                <div>
                    <label for="email" class="block mb-2 text-sm font-medium text-gray-900  text-gray-300">Your email</label>
                    <input type="email" id="email" class="shadow-sm  border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-primary-500 focus:border-primary-500 block w-full p-2.5   border-gray-600    focus:ring-primary-500  focus:border-primary-500  shadow-sm-light" placeholder="name@gmail.com" required>
                </div>
                <div>
                    <label for="subject" class="block mb-2 text-sm font-medium text-gray-900  text-gray-300">Subject</label>
                    <input type="text" id="subject" class="block p-3 w-full text-sm text-gray-900  rounded-lg border border-gray-300 shadow-sm focus:ring-primary-500 focus:border-primary-500   border-gray-600    focus:ring-primary-500  focus:border-primary-500  shadow-sm-light" placeholder="Let us know how we can help you" required>
                </div>
                <div class="sm:col-span-2">
                    <label for="message" class="block mb-2 text-sm font-medium text-gray-900  text-gray-400">Your message</label>
                    <textarea id="message" rows="6" class="block p-2.5 w-full text-sm text-gray-900  rounded-lg shadow-sm border border-gray-300 focus:ring-primary-500 focus:border-primary-500   border-gray-600    focus:ring-primary-500  focus:border-primary-500" placeholder="Leave a comment..."></textarea>
                </div>
                <NuxtLink to="services" class="inline-flex items-center justify-center px-5 py-3 text-base font-medium text-center text-gray-900 border border-gray-300 rounded-lg hover:bg-blue-100 focus:ring-4 focus:ring-gray-100 hover:text-white  border-gray-700  hover:bg-blue-800  focus:ring-blue-800 hover:border-blue-800 w-full">
                    Send Message
                </NuxtLink> 
            </form>
        </div>
        </section>
</template>