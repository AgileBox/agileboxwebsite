<template>
    <section class="privacy">
        <BannerSubpage
            title="Polityka prywatności"
            :breadcrumb-items="[
                    {name: 'Home', href: '/'},
                    {name: 'Polityka prywatności'}
                ]"
        />
        <HeaderAndText
            title="Polityka prywatności"
            subtitle="Skoro jesteś w tej zakładce, to znaczy, że ważne jest dla Ciebie bezpieczeństwo Twoich danych w Sieci. Wiedz, że dbamy o odpowiednie traktowanie Twoich danych osobowych.
            Szanując Twój czas, przygotowałyśmy dla Ciebie skróconą wersję najważniejszych zasad związanych z ochroną prywatności. Jeżeli podstawowe informacje okażą się dla Ciebie niewystarczające, w kolejnych punktach znajdziesz szerszy opis, w którym wyjaśniamy jak obchodzimy się z powierzonymi nam przez Ciebie danymi osobowymi."
        >
            <div class="text-gray-500">
                <h3 class="text-l text-superbold mb-2">I Podstawowe informacje</h3>
                <p class=" mb-4">
                    1. Administratorem danych osobowych na stronie www.agilebox.pl oraz www.akademiascrummastera.pl jesteśmy my, czyli: Luiza Lipień i Dorota Sternalska prowadzące działalność gospodarczą pod firmą AGILE BOX  Dorota Sternalska Luiza Lipień Spółka Cywilna. Możesz się z nami skontaktować w każdej chwili z wykorzystaniem adresu e-mail: kontakt@akademiascrummastera.pl<br>
                    2. Pamiętaj, że podanie danych osobowych, a także zgoda na ich przetwarzanie są całkowicie dobrowolne. Wszelkie przekazane nam dane osobowe są przetwarzane wyłącznie w zakresie i w celu, na jaki wyraziłeś zgodę.<br>
                    3.  W każdej chwili masz prawo do aktualizacji lub całkowitego usunięcia swoich danych osobowych. Możesz to zrobić samodzielnie lub korzystając z naszej pomocy.<br>
                    4. Dbamy o należytą ochronę Twoich danych osobowych, gwarantując Ci, że będą one przetwarzane wyłącznie w celu, na który wyraziłeś zgodę, przechowywane w bezpieczny sposób oraz nieudostępniane podmiotom trzecim, jeżeli nie wyraziłeś na to zgody.<br>
                    5.  Zapisując się na newsletter, webinar, pobierając dokumenty z naszej strony lub dokonując zamówienia, przekazujesz nam swoje dane osobowe, a my gwarantujemy Ci, że Twoje dane pozostaną bezpieczne i nie zostaną udostępnione podmiotom trzecim bez Twojej wyraźnej zgody.<br>
                    6. Korzystamy z narzędzi analitycznych, opisanych poniżej, które zbierają anonimowe informacje na temat Twoich odwiedzin serwisu. Wykorzystuję też narzędzia takie jak Facebook Pixel i Google AdWords, które pozwalają wyświetlać Ci reklamy.<br>
                    7. Podobnie jak ma to miejsce niemal na każdej stronie internetowej, my również wykorzystujemy pliki cookies.
                </p>
            </div>
        </HeaderAndText>
    </section>
</template>

<script>
import BannerSubpage from '~/components/BannerSubpage.vue'
import HeaderAndText from '~/components/HeaderAndText.vue'

export default {
    layout: 'layout',

    components: {
        BannerSubpage,
        HeaderAndText
    },
}
</script>
