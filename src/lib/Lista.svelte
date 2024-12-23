<script>
    import Card from "$lib/Card.svelte";

    let lista = [
        { 
            id: 1,
            name: 'Yamaha R3', 
            cc: 300, 
            price: 9500, 
            transmission: 'Manuale',
            img: "https://cdn.pixabay.com/photo/2020/04/13/21/57/yamaha-yzf-r3-5040161_960_720.jpg"
        },
        { 
            id: 2,
            name: 'Harley Davidson', 
            cc: 1200, 
            price: 11000, 
            transmission: 'Automatico',
            img: "https://cdn.pixabay.com/photo/2022/03/23/07/26/motorcycle-7086569_960_720.jpg"
        },
        { 
            id: 3,
            name: 'Yamaha MT07', 
            cc: 690, 
            price: 8500, 
            transmission: 'Manuale',
            img: "https://cdn.pixabay.com/photo/2021/01/06/12/32/yamaha-5894293_960_720.jpg"
        },
        { 
            id: 4,
            name: 'Ducati 1199', 
            cc: 1200, 
            price: 9000, 
            transmission: 'Manuale',
            img: "https://cdn.pixabay.com/photo/2017/08/02/17/39/biker-2572590_960_720.jpg",        
        },
        { 
            id: 5,
            name: 'Harley Davidson Sportster', 
            cc: 1200, 
            price: 10500, 
            transmission: 'Automatico',
            img: "https://cdn.pixabay.com/photo/2017/04/19/14/35/ducati-2242487_960_720.jpg"
        }
    ];

    function ordineAlfabetico() {
        lista = [...lista].sort((a, b) => a.name.localeCompare(b.name));
    }

    function prezzoCrescente() {
        lista = [...lista].sort((a, b) => a.price - b.price);
    }

    function prezzoDecrescente() {
        lista = [...lista].sort((a, b) => b.price - a.price);
    }

    function cilindrata() {
        lista = [...lista].sort((a, b) => a.cc - b.cc);
    }
</script>

<div class="container mx-auto p-6">
    <h2 class="text-3xl font-bold text-center text-blue-700 mb-6">Lista Moto</h2>

    <div class="text-center mb-6 space-x-4">
        <button class="btn btn-primary bg-blue-600 text-white hover:bg-blue-700 px-6 py-3 rounded-lg shadow-lg" onclick={ordineAlfabetico}>
            Ordine alfabetico
        </button>
        <button class="btn btn-success bg-green-600 text-white hover:bg-green-700 px-6 py-3 rounded-lg shadow-lg" onclick={prezzoCrescente}>
            Ordine prezzo crescente
        </button>
        <button class="btn btn-warning bg-yellow-600 text-white hover:bg-yellow-700 px-6 py-3 rounded-lg shadow-lg" onclick={prezzoDecrescente}>
            Ordine prezzo decrescente
        </button>
        <button class="btn btn-info bg-teal-600 text-white hover:bg-teal-700 px-6 py-3 rounded-lg shadow-lg" onclick={cilindrata}>
            Ordine per cilindrata
        </button>
        <a 
            href="./" 
            class="btn btn-primary text-white bg-red-600 hover:bg-red-700 px-6 py-3 rounded-lg shadow-lg">
            Indietro
        </a>
    </div>

    <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6">
        {#each lista as moto}
            <Card 
                nome={moto.name}
                cilindrata={moto.cc}
                prezzo={moto.price}
                trasmissione={moto.transmission}
                immagine={moto.img}
            />
        {/each}
    </div>
</div>
