<!DOCTYPE html><html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Crypto Market IDR</title>
  <link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css" rel="stylesheet">
  <script src="https://cdn.jsdelivr.net/npm/axios/dist/axios.min.js"></script>
  <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
</head>
<body class="bg-black text-white min-h-screen">
  <div class="p-4 md:p-10">
    <h1 class="text-3xl font-bold mb-6 text-center">Crypto Market (IDR)</h1><div id="tabs" class="flex justify-center space-x-2 mb-6">
  <button onclick="setIntervalTab('1')" class="tab-button px-3 py-1 rounded bg-yellow-500 text-black font-semibold">1D</button>
  <button onclick="setIntervalTab('7')" class="tab-button px-3 py-1 rounded bg-yellow-500 text-black font-semibold">1W</button>
  <button onclick="setIntervalTab('30')" class="tab-button px-3 py-1 rounded bg-yellow-500 text-black font-semibold">1M</button>
  <button onclick="setIntervalTab('365')" class="tab-button px-3 py-1 rounded bg-yellow-500 text-black font-semibold">1Y</button>
</div>

<div id="charts"></div>

<section class="mt-10 p-4 bg-zinc-800 rounded-xl">
  <h2 class="text-2xl font-bold mb-4">Berita Terkini</h2>
  <div id="news-container" class="space-y-4"></div>
</section>

  </div>  <script>
    const coins = ['bitcoin', 'binancecoin', 'solana'];
    let selectedInterval = '1';

    function setIntervalTab(interval) {
      selectedInterval = interval;
      loadCharts();
    }

    async function loadCharts() {
      const container = document.getElementById('charts');
      container.innerHTML = '';

      for (let coin of coins) {
        try {
          const res = await axios.get(`https://api.coingecko.com/api/v3/coins/${coin}/market_chart?vs_currency=idr&days=${selectedInterval}`);

          const prices = res.data.prices.map(([time, price]) => ({
            time: new Date(time).toLocaleDateString(),
            price: Math.round(price)
          }));

          const canvas = document.createElement('div');
          canvas.innerHTML = `
            <div class="bg-zinc-900 rounded-2xl mb-6 shadow-lg p-4">
              <h2 class="text-xl font-semibold mb-2 capitalize">${coin}</h2>
              <canvas id="${coin}-chart" height="250"></canvas>
            </div>
          `;
          container.appendChild(canvas);

          const ctx = document.getElementById(`${coin}-chart`).getContext('2d');
          new Chart(ctx, {
            type: 'line',
            data: {
              labels: prices.map(p => p.time),
              datasets: [{
                label: 'Harga (IDR)',
                data: prices.map(p => p.price),
                borderColor: '#facc15',
                borderWidth: 2,
                fill: false,
                pointRadius: 0
              }]
            },
            options: {
              responsive: true,
              plugins: { legend: { display: false } },
              scales: {
                x: { display: false },
                y: { ticks: { callback: v => 'Rp' + v.toLocaleString() } }
              }
            }
          });
        } catch (err) {
          container.innerHTML += `<p class="text-red-500">Gagal memuat data untuk ${coin}</p>`;
        }
      }
    }

    async function loadNews() {
      const container = document.getElementById('news-container');
      container.innerHTML = '<p>Memuat berita...</p>';

      try {
        const res = await axios.get('https://api.allorigins.win/raw?url=https://news.bitcoin.com/feed/');
        const parser = new DOMParser();
        const xml = parser.parseFromString(res.data, 'application/xml');
        const items = xml.querySelectorAll('item');
        container.innerHTML = '';

        for (let i = 0; i < Math.min(items.length, 5); i++) {
          const item = items[i];
          const title = item.querySelector('title').textContent;
          const link = item.querySelector('link').textContent;
          const pubDate = new Date(item.querySelector('pubDate').textContent).toLocaleDateString('id-ID');
          const description = item.querySelector('description').textContent;

          container.innerHTML += `
            <article class="p-4 bg-zinc-700 rounded-lg">
              <a href="${link}" target="_blank" class="text-xl font-semibold hover:underline">${title}</a>
              <p class="text-sm text-zinc-400">${pubDate}</p>
              <p class="mt-2 text-zinc-200">${description.slice(0, 120)}...</p>
            </article>`;
        }
      } catch (error) {
        container.innerHTML = '<p class="text-red-500">Gagal memuat berita.</p>';
      }
    }

    window.onload = () => {
      loadCharts();
      loadNews();
    };
  </script></body>
</html>
