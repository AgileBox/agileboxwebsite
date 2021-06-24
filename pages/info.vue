<template>
    <section class="aboutUs">
        <BannerSubpage
            title="O nas"
            :image="require('~/static/DSC_6238pp 2.jpg')"
            :breadcrumb-items="[
                {name: 'Home', href: '/'},
                {name: 'O nas'}
            ]"
        />
        <HeaderAndText
            class="text-center"
            title="Łączy nas nie tylko wspólna pasja, ale też wspólne doświadczenie"
        >
        </HeaderAndText>
        <TextAndImage
            :image1="require('~/static/DSC_6322pp.jpg')"
            :image2="require('~/static/DSC_6254pp.jpg')"
        >
            <h3 class="text-gray-500 text-xl font-bold my-1 md:my-4">
                Poznałyśmy się w 2018 roku w William Hill gdzie prowadziłyśmy wspólnie transformację Agilową w ponad 50 zespołach pracujących w różnych lokalizacjach: w Krakowie, Leeds, Londynie i na Gibraltarze.
            </h3>
            <p class="text-gray-500">
                Szybko okazało się, że mamy wiele wspólnego, a szczególnie pasję do dzielenia się wiedzą i wspierania Scrum Masterów, Product Ownerów i managerów w ich codziennej pracy.
            </p>
        </TextAndImage>
        <HeaderAndText
            class="text-center"
            subtitle="Gdybyśmy miały przedstawić nasze wspólne doświadczenie w liczbach, to byłoby to w sumie:"
            is-wide
        >
            <div class="grid grid-cols-12">
                <p class="text-gray-500 mt-6 md:mt-0">
                    <ul class="list-disc p-6">
                        <li>24 lata pracy w IT, w tym 18 lat pracy nad zwinnością</li>
                        <li>21 zespołów, w których pracowałyśmy w roli Scrum Mastera i 60, które wspierałyśmy jako Coach</li>
                        <li>29 Product Ownerów, 83 Scrum Masterów i 49 managerów, z którymi współpracowałyśmy indywidualnie</li>
                        <li>prawie 1000 osób przeszkolonych w zakresie Lean/Agile oraz kompetencji liderskich</li>
                        <li>20 różnych wystąpień i inicjatyw wspierających zwinność: AgileByExample, Agile Warsaw, Scrum Experience Day, Agile &rdquo; Automation Days, Quality Excites, Agile Swarming, Tydzień Facylitacji, ALE Kraków, LeadIT Lady.</li>
                    </ul>
                </p>
            <div>
        </HeaderAndText>
        <HeaderAndText
            class="text-center"
            subtitle="Ale przede wszystkim, połączyło nas wspólne pragnienie - dzielić się z innymi naszą wiedzą i doświadczeniem, pomagać organizacjom i osobom prywatnym w rozwoju. W efekcie stworzyłyśmy “Agile Box” - przestrzeń dla zwinnych liderów."
        >
        </HeaderAndText>
        <div class="bg-gray-50 py-10">
            <div class="wrapper grid grid-cols-12 place-items-center mt-16 mb-6">
                <div class="col-span-12 md:col-span-5">
                    <!-- <h2 class="text-xl font-bold text-gray-700 pb-2">Więcej o</h2> -->
                    <h1 class="text-4xl font-extrabold text-blue-500 mb-8">Luiza Lipień</h1>
                    <p class="text-gray-500 mb-8">Z IT jestem związana od 15 lat. Pełniłam różne funkcje, od kierownika projektu, szefa działu Scrum Masterów, managera działu deweloperskiego, po szefa Agile Coachów. Brałam udział w wielu transformacjach i zmianach organizacyjnych (m.in. w Allegro, PayU, William Hill, GlaxoSmithKline). Dzięki tym doświadczeniom nauczyłam się w jaki sposób tworzyć i wspierać budowanie środowiska, które służy rozwojowi zespołów i jednostek, pozwala im rosnąć i odnosić sukcesy. Nauczyłam się jak być liderem w trudnych i zmiennych warunkach.<br>
                    Obecnie dzielę się swoją wiedzą z innymi - jestem coachem i trenerem zespołów, liderów i managerów w zakresie najlepszych praktyk Lean, Agile, HR oraz rozwoju osobistego.</p>
                </div>
                <div class="img col-span-12 md:col-span-7 md:pl-16">
                    <img src="~/static/DSC_6137pp.jpg" class="shadow-2xl rounded-lg">
                </div>
            </div>
        </div>
        <div class="bg-gray-50 py-10">
            <div class="wrapper grid grid-cols-12 place-items-center mt-6 mb-16">
                <div class="img col-span-12 md:col-span-7 md:pr-16 mb-6 md:mb-0">
                    <img src="~/static/DSC_6423pp2.jpg" class="shadow-2xl rounded-lg">
                </div>
                <div class="col-span-12 md:col-span-5">
                    <!-- <h2 class="text-xl font-bold text-gray-700 pb-2">Więcej o</h2> -->
                    <h1 class="text-4xl font-extrabold text-blue-500 mb-8">Dorota Sternalska</h1>
                    <p class="text-gray-500 mb-8">Swoją przygodę z IT rozpoczęłam ponad 10 lat temu od testowania radiotelefonów dla służb publicznych. Byłam liderem zespołu testowego odpowiedzialnego za strategię testową i koordynowanie testów dla 10 zespołów pracujących nad jednym produktem.<br>
                    Od tamtej pory rozwijam swoje liderskie kompetencje promując zwinne podejście w organizacjach, pracując z zespołami i managerami nad dostarczaniem wartościowych produktów w bardziej efektywny sposób.
</p>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
import BannerSubpage from '~/components/BannerSubpage.vue'
import TextAndImage from '~/components/TextAndImage.vue'
import HeaderAndText from '~/components/HeaderAndText.vue'

export default {
    layout: 'layout',

    components: {
        BannerSubpage,
        TextAndImage,
        HeaderAndText
    },
}
</script>
