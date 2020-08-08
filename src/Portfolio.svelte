<script>
  import PortfolioItem from "./PortfolioItem.svelte";

  const portfolioData = [
    {
      links: [
        {
          url: "https://github.com/Hugo-Persson/T4OrderSystemBackend",
          name: "Source code"
        },
        {
          url: "https://school-order.herokuapp.com/",
          name: "Live Demo"
        }
      ],
      name: "Industri beställning applikation",
      description: `<p>Denna webbapplikationen skapades på uppdrag av en kund, industripogrammet på kattegattgymnasiet, jag jobbade då på
    detta projektet mot dem under mitt tredje år på kattegattgymnasiet.
    Applikationen hanterar beställningar som kunder skickar till industriprogrammet. Admins kan sortera alla
    beställningar och hantera dem,
    varje beställning har en status och kontaktuppgifter som kunden kan se och admins kan uppdatera</p <p>

Backend är byggt med NodeJS med Express och frontend är byggt med hjälp av Svelte och Bootstrap. För inloggning använder
jag mig av passwordless istället för
det normala systemet med ett användarnamn + lösenord. Passwordless bygger på att inga konton har lösenord, istället så
skickas en verifikations kod till användarna
när de loggar in. Jag valde passwordless då det skapar större säkerhet för kunden. Jag använde mig av MongoDB för att
spara alla användare och beställningar.

</p>
<p>
    För att se sidan kan ni klicka på live demo, för att komma åt kundportalen är det bara att skriva in en e-mail och
    skapa ett konto, om ni vill se adminsidan
    kan ni använda e-mailen "adminSiteDemo@example.com", detta kontot har behöver inte verifieras med en kod för demo
    verisionen av sidan.
</p>`,
      skills: [
        {
          name: "JavaScript",
          icon: "devicon-javascript-plain colored"
        },
        {
          name: "Svelte",
          icon: "/svelte.png"
        },

        {
          name: "Bootstrap",
          icon: "devicon-bootstrap-plain colored"
        },
        {
          name: "NodeJS",
          icon: "devicon-nodejs-plain colored"
        },
        {
          name: "Express",
          icon: "devicon-express-original colored"
        },
        {
          name: "MongoDB",
          icon: "devicon-mongodb-plain colored"
        }
      ]
    },
    {
      links: [
        {
          url: "https://github.com/Hugo-Persson/CrunchyrollPlusXamarin",
          name: "Source code"
        }
      ],
      name: "Xamarin forms streaming app",
      description:
        "Esse mollit exercitation esse amet nostrud amet ex mollit non. Consequat anim in ex eu laboris et officia.Irure proident nostrud sunt fugiat est officia eu sit mollit. Mollit aliquip ipsum dolor culpa. Occaecat velit proident aliqua culpa eu elit ad velit pariatur aliquip. Elit sint tempor quis reprehenderit magna elit amet aute laboris. In dolore nostrud cupidatat nisi id laboris esse nulla et quis non. Excepteur ullamco quis sint excepteur esse veniam Lorem nisi cupidatat. Sit nostrud adipisicing in cillum velit. Ad ex dolor nostrud mollit. Est dolor amet consequat officia. Eu qui dolore mollit reprehenderit commodo mollit ex dolor tempor sunt proident. Tempor veniam sint nostrud dolore exercitation nostrud est laboris minim quis nulla. Duis anim tempor aute nulla velit duis voluptate voluptate anim sit cupidatat esse cupidatat.",
      skills: [
        {
          name: "C#",
          icon: "devicon-csharp-plain colored"
        },
        {
          name: "Xamarin Forms",
          icon: "xamarin_logo.png"
        }
      ]
    }
  ];
</script>

{#each portfolioData as item}
  <PortfolioItem {item} />
{/each}
