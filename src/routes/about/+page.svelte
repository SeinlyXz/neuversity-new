<script>
  const values = [
    "Inovasi Digital",
    "Kolaborasi Mahasiswa",
    "Pembelajaran Berkelanjutan",
    "Teknologi untuk Dampak Nyata"
  ];
</script>

<section class="min-h-screen bg-gray-50 py-16 px-6">
  <div class="max-w-5xl mx-auto">
    <!-- Title -->
    <div class="text-center mb-12">
      <h1 class="text-4xl md:text-5xl font-bold text-gray-800 mb-4">
        Tentang Neuversity
      </h1>
      <p class="text-gray-600 text-lg">
        Universitas digital untuk generasi pembelajar masa depan
      </p>
    </div>

    <!-- Content -->
    <div class="grid md:grid-cols-2 gap-10 items-center">
      <div>
        <h2 class="text-2xl font-semibold text-indigo-600 mb-4">
          Apa itu Neuversity?
        </h2>
        <p class="text-gray-700 leading-relaxed mb-6">
          <strong>Neuversity</strong> adalah platform edukasi modern yang
          dirancang untuk mahasiswa yang ingin berkembang di era digital.
          Neuversity menggabungkan teknologi, komunitas, dan pembelajaran praktis
          untuk menciptakan pengalaman belajar yang relevan dengan kebutuhan industri.
        </p>

        <p class="text-gray-700 leading-relaxed">
          Kami percaya bahwa pendidikan tidak hanya soal teori, tetapi juga
          tentang eksplorasi, kolaborasi, dan penerapan nyata.
        </p>
      </div>

      <!-- Values -->
      <div class="bg-white rounded-2xl shadow-lg p-8">
        <h3 class="text-xl font-semibold text-gray-800 mb-6">
          Nilai Utama Neuversity
        </h3>

        <ul class="space-y-4">
          {#each values as value}
            <li class="flex items-center gap-3">
              <span class="w-3 h-3 rounded-full bg-indigo-500"></span>
              <span class="text-gray-700 font-medium">{value}</span>
            </li>
          {/each}
        </ul>
      </div>
    </div>
  </div>
</section>
