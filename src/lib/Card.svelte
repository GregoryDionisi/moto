<script>
    let { nome = "---", cilindrata = "---", prezzo = "---", trasmissione = "---", immagine = "---" } = $props();
</script>

<div class="bg-white p-4 rounded-lg shadow-lg hover:shadow-xl transition-all duration-300">
    <img class="w-full h-64 object-cover rounded-lg mb-4" src={immagine} alt="Immagine della moto">
    <h3 class="text-xl font-semibold text-blue-700">{nome}</h3>
    <p class="text-gray-700 mt-2">Cilindrata: {cilindrata} cc</p>
    <p class="text-gray-700 mt-1">Prezzo: {prezzo}€</p>
    <p class="text-gray-700 mt-1">Trasmissione: {trasmissione}</p>
</div>
