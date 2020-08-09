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
        },
        {
          url:
            "https://drive.google.com/file/d/1XqmtVD6bfMzROGm3Jfsyvl9DcgNA6dmr/view?usp=sharing",
          name: "Ladda ner APK"
        }
      ],
      name: "Xamarin forms video streaming app",
      description: `<p>
        Detta projektet är en mobil app jag skapade i Xamarin Forms, appen är en streaming app som förmedlar video från
        Crunchyroll.com API.
        Jag skapade appen då jag kände att den crunchyroll appen som finns kan förbättras på flera sätt. För att testa appen
        kan ni ladda ner och installera APK filen
        eller clona git repositoryt och bygga projektet. Appen fungerar både på Android och IOS men det är inte publicerad
        på App Store eller Play Store så för att testa
        appen för IOS måste ni bygga projektet till er IOS enhet.




        </p>`,
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
    },
    {
      links: [
        {
          url: "https://github.com/Hugo-Persson/OnePaceStreamer",
          name: "Source code"
        },
        {
          url: "https://one-pace-stream.herokuapp.com/",
          name: "Live Demo"
        }
      ],
      name: "Torrent streaming applikation",
      description: `
        <p>
            Denna webbapplikationen är gjord för att kunna streama en torrent på ett enkelt sätt. Applikation gör så att
            användaren inte behöver installera någon torrent programvara
            så som BitTorrent istället så gör servern det och streamar videon direkt till användaren. Detta gör en stor skillnad
            på mobila enheter där det kan vara komplicerat
            att använda torrent program.
        </p>
        <p>
            Programmet använder WebTorrent och NodeJS för att göra om torrenten till en stream som sedan en media spelar så som
            VLC kan stream direkt. Du skulle även
            kunna streama median direkt i webbläsaren men filformatet är .mkv vilket webbläsarna inte stödjer.

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
          name: "NodeJS",
          icon: "devicon-nodejs-plain colored"
        },
        {
          name: "Express",
          icon: "devicon-express-original colored"
        }
      ]
    }
  ];
</script>

{#each portfolioData as item}
  <PortfolioItem {item} />
{/each}
