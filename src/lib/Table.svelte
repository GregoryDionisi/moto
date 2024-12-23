<script>
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
    ]

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
    <h2 class="text-3xl font-bold text-center text-blue-700 mb-6">Tabella delle Moto</h2>

    <div class="text-center mb-6 space-x-4">
        <button class="btn btn-primary text-white" onclick={ordineAlfabetico}>Ordine alfabetico</button>
        <button class="btn btn-success text-white" onclick={prezzoCrescente}>Ordine prezzo crescente</button>
        <button class="btn btn-warning text-white" onclick={prezzoDecrescente}>Ordine prezzo decrescente</button>
        <button class="btn btn-info text-white" onclick={cilindrata}>Ordine per cilindrata</button>
        <a 
            href="./" 
            class="btn btn-primary text-white bg-red-600 hover:bg-red-700 px-6 py-3 rounded-lg shadow-lg">
            Indietro
        </a>
    </div>

    <table class="table table-striped w-full border-collapse bg-white shadow-lg text-black">
        <thead class="text-black">
            <tr>
                <th class="p-4 border-b text-left">Nome</th>
                <th class="p-4 border-b text-left">Cilindrata</th>
                <th class="p-4 border-b text-left">Prezzo</th>
                <th class="p-4 border-b text-left">Trasmissione</th>
            </tr>
        </thead>
        <tbody class="text-black">
            {#each lista as moto}
                <tr>
                    <td class="p-4 border-b">{moto.name}</td>
                    <td class="p-4 border-b">{moto.cc}</td>
                    <td class="p-4 border-b">{moto.price}€</td>
                    <td class="p-4 border-b">{moto.transmission}</td>
                </tr>
            {/each}
        </tbody>        
    </table>
</div>
