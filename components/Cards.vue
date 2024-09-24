<template>
    <div class="cards">
        <div class="max-w-sm bg-white border border-gray-200 rounded-lg shadow dark:bg-gray-800 dark:border-gray-700">
            <a href="https://simonmaigrot.github.io/">
                <img class="rounded-t-lg" src="assets/portfolio.png" alt="" />
            </a>
            <div class="p-5">
                <a href="#">
                    <h5 class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white">Portfolio</h5>
                </a>
                <p class="mb-3 font-normal text-gray-700 dark:text-gray-400">Voici mon ancien portfolio que j'avais crée au lycée pour un projet web</p>
                <a href="https://simonmaigrot.github.io/" target="_blank" class="inline-flex items-center px-3 py-2 text-sm font-medium text-center text-white bg-blue-700 rounded-lg hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800 mt-2">
                    Visiter
                    <svg class="rtl:rotate-180 w-3.5 h-3.5 ms-2" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 14 10">
                        <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M1 5h12m0 0L9 1m4 4L9 9"/>
                    </svg>
                </a>
            </div>
        </div>
        <div class="max-w-sm bg-white border border-gray-200 rounded-lg shadow dark:bg-gray-800 dark:border-gray-700">
            <a href="https://www.wakatepe.fr/">
                <img class="rounded-t-lg" src="assets/wakatepe.png" alt="" />
            </a>
            <div class="p-5">
                <a href="#">
                    <h5 class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white">Wakatepe</h5>
                </a>
                <p class="mb-3 font-normal text-gray-700 dark:text-gray-400">Actuellement en deuxième année à Epitech, j'ai la chance d'effectuer un stage en développement web chez Wakatepe.</p>
                <a href="https://www.wakatepe.fr/" target="_blank" class="inline-flex items-center px-3 py-2 text-sm font-medium text-center text-white bg-blue-700 rounded-lg hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800 mt-2">
                    Visiter
                    <svg class="rtl:rotate-180 w-3.5 h-3.5 ms-2" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 14 10">
                        <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M1 5h12m0 0L9 1m4 4L9 9"/>
                    </svg>
                </a>
            </div>
        </div>
    </div>
</template>

<style scoped>
.cards {
    display: flex;
    flex-direction: column;
    gap: 50px;
    margin-left: 30px;
    margin-right: 30px;
}

@media screen and (min-width: 767px) {
    .cards {
        margin-top: 100px;
        flex-direction: row;
    }
}
</style>