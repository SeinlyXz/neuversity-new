<script>
	import { onMount } from 'svelte';
	
	let isVisible = false;
	
	onMount(() => {
		isVisible = true;
	});

	const programs = [
		{
			title: 'Full-Stack Development',
			description: 'Pelajari pengembangan web lengkap dari frontend hingga backend',
			icon: '🌐',
			duration: '6 Bulan'
		},
		{
			title: 'Mobile Development',
			description: 'Bangun aplikasi mobile native dan cross-platform',
			icon: '📱',
			duration: '5 Bulan'
		},
		{
			title: 'DevOps & Cloud',
			description: 'Kuasai deployment, CI/CD, dan infrastruktur cloud',
			icon: '☁️',
			duration: '4 Bulan'
		}
	];
</script>

<svelte:head>
	<title>Neuversity - Sekolah Software Engineering</title>
	<meta name="description" content="Belajar software engineering dengan metode praktis dan mentor berpengalaman" />
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
					<a href="" class="text-gray-700 hover:text-blue-600 transition">Beranda</a>
					<a href="/blog" class="text-gray-700 hover:text-blue-600 transition">Blog</a>
					<a href="/about" class="text-gray-700 hover:text-blue-600 transition">Tentang</a>
					<a href="/contact" class="text-gray-700 hover:text-blue-600 transition">Kontak</a>
				</div>
				<button class="bg-blue-600 text-white px-6 py-2 rounded-lg hover:bg-blue-700 transition">
					Daftar Sekarang
				</button>
			</div>
		</div>
	</nav>

	<!-- Hero Section -->
	<section class="bg-white">
		<div class="container mx-auto px-6 py-20">
			<div class="grid md:grid-cols-2 gap-12 items-center">
				<div>
					<div class="inline-block mb-4 px-4 py-2 bg-blue-50 rounded-full">
						<span class="text-blue-600 text-sm font-medium">🎓 School of Software Engineering</span>
					</div>
					
					<h1 class="text-5xl md:text-6xl font-bold text-gray-900 mb-6 leading-tight">
						Mulai Karir di Dunia <span class="text-blue-600">Software Engineering</span>
					</h1>
					
					<p class="text-xl text-gray-600 mb-8 leading-relaxed">
						Belajar coding dari dasar hingga mahir dengan metode praktis, project nyata, dan bimbingan mentor profesional.
					</p>
					
					<div class="flex flex-col sm:flex-row gap-4">
						<button class="px-8 py-4 bg-blue-600 text-white rounded-lg font-semibold hover:bg-blue-700 transition shadow-lg shadow-blue-200">
							Mulai Belajar
						</button>
						<button class="px-8 py-4 bg-gray-100 text-gray-900 rounded-lg font-semibold hover:bg-gray-200 transition">
							Lihat Kurikulum
						</button>
					</div>

					<div class="mt-12 flex items-center gap-8">
						<div>
							<div class="text-3xl font-bold text-gray-900">500+</div>
							<div class="text-gray-600">Alumni</div>
						</div>
						<div>
							<div class="text-3xl font-bold text-gray-900">95%</div>
							<div class="text-gray-600">Tingkat Kelulusan</div>
						</div>
						<div>
							<div class="text-3xl font-bold text-gray-900">4.8/5</div>
							<div class="text-gray-600">Rating</div>
						</div>
					</div>
				</div>
				
				<div class="relative">
					<div class="bg-gradient-to-br from-blue-100 to-indigo-100 rounded-3xl p-8 shadow-xl">
						<img src="/api/placeholder/500/400" alt="Learning" class="rounded-2xl w-full" />
					</div>
					<div class="absolute -bottom-6 -left-6 bg-white p-6 rounded-2xl shadow-lg">
						<div class="flex items-center gap-4">
							<div class="w-12 h-12 bg-green-100 rounded-full flex items-center justify-center">
								<span class="text-2xl">✓</span>
							</div>
							<div>
								<div class="font-semibold text-gray-900">Sertifikat Resmi</div>
								<div class="text-sm text-gray-600">Setelah lulus program</div>
							</div>
						</div>
					</div>
				</div>
			</div>
		</div>
	</section>

	<!-- Program Section -->
	<section class="py-20 bg-gray-50">
		<div class="container mx-auto px-6">
			<div class="text-center mb-16">
				<h2 class="text-4xl font-bold text-gray-900 mb-4">
					Program Belajar Kami
				</h2>
				<p class="text-xl text-gray-600 max-w-2xl mx-auto">
					Pilih program yang sesuai dengan minat dan tujuan karir kamu
				</p>
			</div>
			
			<div class="grid md:grid-cols-3 gap-8 max-w-6xl mx-auto">
				{#each programs as program}
					<div class="bg-white rounded-2xl p-8 hover:shadow-xl transition border border-gray-200">
						<div class="w-16 h-16 bg-blue-50 rounded-xl flex items-center justify-center mb-6">
							<span class="text-4xl">{program.icon}</span>
						</div>
						<h3 class="text-2xl font-bold text-gray-900 mb-3">{program.title}</h3>
						<p class="text-gray-600 mb-6">{program.description}</p>
						<div class="flex items-center justify-between">
							<span class="text-sm text-gray-500">Durasi: {program.duration}</span>
							<button class="text-blue-600 font-semibold hover:text-blue-700">
								Pelajari →
							</button>
						</div>
					</div>
				{/each}
			</div>
		</div>
	</section>

	<!-- Why Us Section -->
	<section class="py-20 bg-white">
		<div class="container mx-auto px-6">
			<div class="grid md:grid-cols-2 gap-12 items-center">
				<div>
					<h2 class="text-4xl font-bold text-gray-900 mb-6">
						Kenapa Belajar di Neuversity?
					</h2>
					<div class="space-y-6">
						<div class="flex gap-4">
							<div class="w-12 h-12 bg-blue-100 rounded-lg flex items-center justify-center flex-shrink-0">
								<span class="text-xl">💼</span>
							</div>
							<div>
								<h3 class="text-xl font-semibold text-gray-900 mb-2">Project Real-World</h3>
								<p class="text-gray-600">Bangun portfolio dengan mengerjakan project yang digunakan di industri sesungguhnya.</p>
							</div>
						</div>
						
						<div class="flex gap-4">
							<div class="w-12 h-12 bg-blue-100 rounded-lg flex items-center justify-center flex-shrink-0">
								<span class="text-xl">👨‍🏫</span>
							</div>
							<div>
								<h3 class="text-xl font-semibold text-gray-900 mb-2">Mentor Berpengalaman</h3>
								<p class="text-gray-600">Dibimbing langsung oleh praktisi yang sudah malang melintang di industri tech.</p>
							</div>
						</div>
						
						<div class="flex gap-4">
							<div class="w-12 h-12 bg-blue-100 rounded-lg flex items-center justify-center flex-shrink-0">
								<span class="text-xl">🎯</span>
							</div>
							<div>
								<h3 class="text-xl font-semibold text-gray-900 mb-2">Pembelajaran Terstruktur</h3>
								<p class="text-gray-600">Kurikulum yang dirancang sistematis dari basic hingga advanced level.</p>
							</div>
						</div>

						<div class="flex gap-4">
							<div class="w-12 h-12 bg-blue-100 rounded-lg flex items-center justify-center flex-shrink-0">
								<span class="text-xl">🤝</span>
							</div>
							<div>
								<h3 class="text-xl font-semibold text-gray-900 mb-2">Komunitas Aktif</h3>
								<p class="text-gray-600">Bergabung dengan komunitas developer yang saling support dan berkembang bersama.</p>
							</div>
						</div>
					</div>
				</div>
				
				<div class="bg-gradient-to-br from-gray-100 to-gray-50 rounded-3xl p-8">
					<img src="/api/placeholder/500/500" alt="Students" class="rounded-2xl w-full" />
				</div>
			</div>
		</div>
	</section>

	<!-- Tech Stack -->
	<section class="py-20 bg-gray-900 text-white">
		<div class="container mx-auto px-6">
			<div class="text-center mb-16">
				<h2 class="text-4xl font-bold mb-4">Teknologi yang Dipelajari</h2>
				<p class="text-xl text-gray-400">Tools dan framework yang digunakan perusahaan tech terkemuka</p>
			</div>
			
			<div class="grid grid-cols-2 md:grid-cols-4 gap-6 max-w-5xl mx-auto">
				{#each ['JavaScript', 'TypeScript', 'React', 'Vue.js', 'Node.js', 'Python', 'PostgreSQL', 'MongoDB', 'Docker', 'AWS', 'Git', 'Linux'] as tech}
					<div class="bg-gray-800 rounded-xl p-6 text-center hover:bg-gray-700 transition border border-gray-700">
						<div class="text-gray-300 font-medium">{tech}</div>
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
					Siap Memulai Perjalanan Belajar?
				</h2>
				<p class="text-xl mb-8 text-blue-100">
					Daftar sekarang dan dapatkan akses ke semua materi pembelajaran, project, dan mentoring
				</p>
				<div class="flex flex-col sm:flex-row gap-4 justify-center">
					<button class="px-8 py-4 bg-white text-blue-600 rounded-lg font-semibold hover:bg-gray-100 transition shadow-lg">
						Daftar Sekarang
					</button>
					<button class="px-8 py-4 bg-transparent border-2 border-white text-white rounded-lg font-semibold hover:bg-white hover:text-blue-600 transition">
						Konsultasi Gratis
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
						<li><a href="#" class="hover:text-white transition">Tentang Kami</a></li>
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