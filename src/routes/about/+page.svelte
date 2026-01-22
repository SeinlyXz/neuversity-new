<script>
	const values = [
		{
			icon: '💡',
			title: 'Inovasi Digital',
			description: 'Mengadopsi teknologi terkini dalam proses pembelajaran'
		},
		{
			icon: '🤝',
			title: 'Kolaborasi Mahasiswa',
			description: 'Membangun komunitas yang saling mendukung dan berkembang'
		},
		{
			icon: '📚',
			title: 'Pembelajaran Berkelanjutan',
			description: 'Komitmen untuk terus belajar dan mengikuti perkembangan industri'
		},
		{
			icon: '🎯',
			title: 'Teknologi untuk Dampak Nyata',
			description: 'Fokus pada solusi yang memberikan nilai bagi masyarakat'
		}
	];

	const team = [
		{
			name: 'Ahmad Fauzi',
			role: 'Founder & Lead Instructor',
			image: '/api/placeholder/200/200'
		},
		{
			name: 'Sarah Putri',
			role: 'Head of Curriculum',
			image: '/api/placeholder/200/200'
		},
		{
			name: 'Budi Santoso',
			role: 'Tech Lead',
			image: '/api/placeholder/200/200'
		}
	];
</script>

<svelte:head>
	<title>Tentang Kami - Neuversity</title>
	<meta name="description" content="Pelajari lebih lanjut tentang Neuversity, visi, misi, dan tim kami" />
</svelte:head>

<div class="bg-gray-50">
	<!-- Navigation -->
	<nav class="bg-white border-b border-gray-200">
		<div class="container mx-auto px-6 py-4">
			<div class="flex items-center justify-between">
				<div class="flex items-center space-x-2">
					<div class="w-10 h-10 bg-blue-600 rounded-lg flex items-center justify-center">
						<span class="text-white font-bold text-xl">N</span>
					</div>
					<span class="text-xl font-bold text-gray-900">Neuversity</span>
				</div>
				<div class="hidden md:flex space-x-8">
					<a href="/" class="text-gray-700 hover:text-blue-600 transition">Beranda</a>
					<a href="#" class="text-gray-700 hover:text-blue-600 transition">Blog</a>
					<a href="/about" class="text-blue-600 font-semibold">Tentang</a>
					<a href="#" class="text-gray-700 hover:text-blue-600 transition">Kontak</a>
				</div>
				<button class="bg-blue-600 text-white px-6 py-2 rounded-lg hover:bg-blue-700 transition">
					Daftar Sekarang
				</button>
			</div>
		</div>
	</nav>

	<!-- Hero Section -->
	<section class="bg-white py-16">
		<div class="container mx-auto px-6">
			<div class="text-center max-w-3xl mx-auto">
				<div class="inline-block mb-4 px-4 py-2 bg-blue-50 rounded-full">
					<span class="text-blue-600 text-sm font-medium">✨ Tentang Kami</span>
				</div>
				<h1 class="text-5xl md:text-6xl font-bold text-gray-900 mb-6">
					Membangun Generasi <span class="text-blue-600">Developer</span> Masa Depan
				</h1>
				<p class="text-xl text-gray-600 leading-relaxed">
					Platform edukasi modern yang menggabungkan teknologi, komunitas, dan pembelajaran praktis untuk menciptakan pengalaman belajar yang relevan.
				</p>
			</div>
		</div>
	</section>

	<!-- Story Section -->
	<section class="py-20 bg-gray-50">
		<div class="container mx-auto px-6">
			<div class="grid md:grid-cols-2 gap-12 items-center max-w-6xl mx-auto">
				<div class="bg-gradient-to-br from-blue-100 to-indigo-100 rounded-3xl p-8">
					<img src="/api/placeholder/500/400" alt="Neuversity Story" class="rounded-2xl w-full" />
				</div>
				
				<div>
					<h2 class="text-4xl font-bold text-gray-900 mb-6">
						Apa itu Neuversity?
					</h2>
					<p class="text-gray-700 text-lg leading-relaxed mb-6">
						<strong>Neuversity</strong> adalah platform edukasi modern yang dirancang untuk mahasiswa yang ingin berkembang di era digital. Kami menggabungkan teknologi, komunitas, dan pembelajaran praktis untuk menciptakan pengalaman belajar yang relevan dengan kebutuhan industri.
					</p>
					<p class="text-gray-700 text-lg leading-relaxed mb-8">
						Kami percaya bahwa pendidikan tidak hanya soal teori, tetapi juga tentang eksplorasi, kolaborasi, dan penerapan nyata. Setiap siswa memiliki potensi untuk menjadi developer profesional dengan bimbingan yang tepat.
					</p>
					
					<div class="grid grid-cols-3 gap-6">
						<div>
							<div class="text-3xl font-bold text-blue-600 mb-1">500+</div>
							<div class="text-gray-600 text-sm">Alumni</div>
						</div>
						<div>
							<div class="text-3xl font-bold text-blue-600 mb-1">50+</div>
							<div class="text-gray-600 text-sm">Mentor</div>
						</div>
						<div>
							<div class="text-3xl font-bold text-blue-600 mb-1">100+</div>
							<div class="text-gray-600 text-sm">Perusahaan Mitra</div>
						</div>
					</div>
				</div>
			</div>
		</div>
	</section>

	<!-- Values Section -->
	<section class="py-20 bg-white">
		<div class="container mx-auto px-6">
			<div class="text-center mb-16">
				<h2 class="text-4xl font-bold text-gray-900 mb-4">
					Nilai Utama Neuversity
				</h2>
				<p class="text-xl text-gray-600 max-w-2xl mx-auto">
					Prinsip-prinsip yang menjadi fondasi dalam setiap program dan kegiatan kami
				</p>
			</div>

			<div class="grid md:grid-cols-2 lg:grid-cols-4 gap-8 max-w-6xl mx-auto">
				{#each values as value}
					<div class="bg-white rounded-2xl p-8 border border-gray-200 hover:shadow-xl transition">
						<div class="w-16 h-16 bg-blue-50 rounded-xl flex items-center justify-center mb-6">
							<span class="text-4xl">{value.icon}</span>
						</div>
						<h3 class="text-xl font-bold text-gray-900 mb-3">{value.title}</h3>
						<p class="text-gray-600">{value.description}</p>
					</div>
				{/each}
			</div>
		</div>
	</section>

	<!-- Mission & Vision -->
	<section class="py-20 bg-gray-50">
		<div class="container mx-auto px-6">
			<div class="grid md:grid-cols-2 gap-12 max-w-6xl mx-auto">
				<div class="bg-white rounded-3xl p-10 border border-gray-200">
					<div class="w-12 h-12 bg-blue-100 rounded-xl flex items-center justify-center mb-6">
						<span class="text-2xl">🎯</span>
					</div>
					<h3 class="text-3xl font-bold text-gray-900 mb-4">Misi Kami</h3>
					<p class="text-gray-700 text-lg leading-relaxed">
						Memberikan akses pendidikan software engineering berkualitas tinggi yang terjangkau dan relevan dengan kebutuhan industri, serta membangun komunitas developer yang saling mendukung dan terus berkembang.
					</p>
				</div>

				<div class="bg-white rounded-3xl p-10 border border-gray-200">
					<div class="w-12 h-12 bg-blue-100 rounded-xl flex items-center justify-center mb-6">
						<span class="text-2xl">🚀</span>
					</div>
					<h3 class="text-3xl font-bold text-gray-900 mb-4">Visi Kami</h3>
					<p class="text-gray-700 text-lg leading-relaxed">
						Menjadi platform edukasi teknologi terdepan di Indonesia yang menghasilkan developer profesional berkualitas dan siap berkontribusi dalam membangun ekosistem teknologi yang lebih baik.
					</p>
				</div>
			</div>
		</div>
	</section>

	<!-- Team Section -->
	<section class="py-20 bg-white">
		<div class="container mx-auto px-6">
			<div class="text-center mb-16">
				<h2 class="text-4xl font-bold text-gray-900 mb-4">
					Tim Kami
				</h2>
				<p class="text-xl text-gray-600 max-w-2xl mx-auto">
					Bertemu dengan para mentor dan instruktur berpengalaman
				</p>
			</div>

			<div class="grid md:grid-cols-3 gap-8 max-w-5xl mx-auto">
				{#each team as member}
					<div class="text-center">
						<div class="mb-6">
							<img src={member.image} alt={member.name} class="w-48 h-48 rounded-2xl mx-auto object-cover border-4 border-gray-100" />
						</div>
						<h3 class="text-xl font-bold text-gray-900 mb-2">{member.name}</h3>
						<p class="text-gray-600">{member.role}</p>
					</div>
				{/each}
			</div>
		</div>
	</section>

	<!-- CTA Section -->
	<section class="py-20 bg-blue-600">
		<div class="container mx-auto px-6">
			<div class="max-w-4xl mx-auto text-center text-white">
				<h2 class="text-4xl md:text-5xl font-bold mb-6">
					Siap Bergabung dengan Neuversity?
				</h2>
				<p class="text-xl mb-8 text-blue-100">
					Mari bersama-sama membangun karir di dunia teknologi
				</p>
				<div class="flex flex-col sm:flex-row gap-4 justify-center">
					<button class="px-8 py-4 bg-white text-blue-600 rounded-lg font-semibold hover:bg-gray-100 transition shadow-lg">
						Daftar Sekarang
					</button>
					<button class="px-8 py-4 bg-transparent border-2 border-white text-white rounded-lg font-semibold hover:bg-white hover:text-blue-600 transition">
						Hubungi Kami
					</button>
				</div>
			</div>
		</div>
	</section>

	<!-- Footer -->
	<footer class="bg-gray-900 text-gray-400 py-12">
		<div class="container mx-auto px-6">
			<div class="grid md:grid-cols-4 gap-8">
				<div>
					<div class="flex items-center space-x-2 mb-4">
						<div class="w-10 h-10 bg-blue-600 rounded-lg flex items-center justify-center">
							<span class="text-white font-bold text-xl">N</span>
						</div>
						<span class="text-xl font-bold text-white">Neuversity</span>
					</div>
					<p class="text-sm">Belajar software engineering dengan cara yang lebih efektif dan menyenangkan.</p>
				</div>
				
				<div>
					<h4 class="text-white font-semibold mb-4">Program</h4>
					<ul class="space-y-2 text-sm">
						<li><a href="#" class="hover:text-white transition">Full-Stack</a></li>
						<li><a href="#" class="hover:text-white transition">Mobile Dev</a></li>
						<li><a href="#" class="hover:text-white transition">DevOps</a></li>
					</ul>
				</div>
				
				<div>
					<h4 class="text-white font-semibold mb-4">Perusahaan</h4>
					<ul class="space-y-2 text-sm">
						<li><a href="/about" class="hover:text-white transition">Tentang Kami</a></li>
						<li><a href="#" class="hover:text-white transition">Karir</a></li>
						<li><a href="#" class="hover:text-white transition">Blog</a></li>
					</ul>
				</div>
				
				<div>
					<h4 class="text-white font-semibold mb-4">Kontak</h4>
					<ul class="space-y-2 text-sm">
						<li>Email: hello@neuversity.id</li>
						<li>Telp: +62 812-3456-7890</li>
						<li>Bandung, Indonesia</li>
					</ul>
				</div>
			</div>
			
			<div class="border-t border-gray-800 mt-12 pt-8 text-sm text-center">
				<p>&copy; 2024 Neuversity. All rights reserved.</p>
			</div>
		</div>
	</footer>
</div>