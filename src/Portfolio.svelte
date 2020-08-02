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
      description:
        "Esse mollit exercitation esse amet nostrud amet ex mollit non. Consequat anim in ex eu laboris et officia.Irure proident nostrud sunt fugiat est officia eu sit mollit. Mollit aliquip ipsum dolor culpa. Occaecat velit proident aliqua culpa eu elit ad velit pariatur aliquip. Elit sint tempor quis reprehenderit magna elit amet aute laboris. In dolore nostrud cupidatat nisi id laboris esse nulla et quis non. Excepteur ullamco quis sint excepteur esse veniam Lorem nisi cupidatat. Sit nostrud adipisicing in cillum velit. Ad ex dolor nostrud mollit. Est dolor amet consequat officia. Eu qui dolore mollit reprehenderit commodo mollit ex dolor tempor sunt proident. Tempor veniam sint nostrud dolore exercitation nostrud est laboris minim quis nulla. Duis anim tempor aute nulla velit duis voluptate voluptate anim sit cupidatat esse cupidatat.",
      skills: [
        {
          name: "JavaScript",
          icon: "devicon-javascript-plain colored"
        },
        {
          name: "Svelte"
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
        }
      ]
    }
  ];
</script>

{#each portfolioData as item}
  <PortfolioItem {item} />
{/each}
