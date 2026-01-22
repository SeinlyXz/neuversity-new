<script>
    import { page } from '$app/stores';
    
    $: postId = $page.params.slug;
    
    const article = {
        id: 1,
        title: "Membangun Karier di Era AI: Panduan Lengkap untuk Pemula",
        excerpt: "Pelajari bagaimana artificial intelligence mengubah landscape karier teknologi dan bagaimana Anda bisa mempersiapkan diri untuk masa depan yang penuh dengan peluang.",
        category: "AI & Career",
        author: {
            name: "Andi Pratama",
            avatar: "https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?w=100&h=100&fit=crop&crop=face",
            role: "Head of AI Program",
            bio: "Praktisi AI dengan pengalaman 10+ tahun. Lulusan MIT dan mantan researcher di Google AI.",
            social: { twitter: "#", linkedin: "#", github: "#" }
        },
        date: "15 Januari 2025",
        readTime: "8 min read",
        image: "https://images.unsplash.com/photo-1677442136019-21780ecad995?w=1200&h=600&fit=crop",
        tags: ["AI", "Career", "Technology", "Machine Learning", "Future"],
        content: `
            <p class="lead">Era kecerdasan buatan telah tiba, dan dampaknya terhadap dunia kerja tidak bisa diabaikan. Menurut World Economic Forum, 85 juta pekerjaan akan tergantikan oleh AI pada tahun 2025, namun 97 juta pekerjaan baru akan muncul.</p>

            <h2>Memahami Lanskap AI Saat Ini</h2>
            <p>Artificial Intelligence bukan lagi konsep futuristik. Dari rekomendasi Netflix hingga diagnosa medis, AI sudah ada di mana-mana.</p>
            <p>Di Neuversity, kami melihat langsung bagaimana permintaan untuk skill AI meningkat drastis. Perusahaan-perusahaan di Yogyakarta dan seluruh Indonesia aktif mencari talent dengan kemampuan:</p>
            <ul>
                <li><strong>Machine Learning Engineering</strong> - Membangun dan deploy model ML</li>
                <li><strong>Data Science</strong> - Mengekstrak insight dari data</li>
                <li><strong>MLOps</strong> - Mengelola lifecycle model AI di production</li>
                <li><strong>AI Product Management</strong> - Merancang produk berbasis AI</li>
                <li><strong>Prompt Engineering</strong> - Mengoptimalkan interaksi dengan LLM</li>
            </ul>

            <h2>Skill Fundamental yang Wajib Dikuasai</h2>
            <h3>1. Programming dengan Python</h3>
            <p>Python adalah lingua franca dunia AI. Hampir semua library ML utama dibuat dengan Python.</p>
            <pre><code class="language-python"># Contoh sederhana training model
from sklearn.model_selection import train_test_split
from sklearn.ensemble import RandomForestClassifier

X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2)
model = RandomForestClassifier(n_estimators=100)
model.fit(X_train, y_train)
accuracy = model.score(X_test, y_test)
print(f"Accuracy: {accuracy:.2%}")</code></pre>

            <h3>2. Matematika & Statistik</h3>
            <p>Pemahaman solid tentang linear algebra, calculus, dan probability sangat membantu.</p>

            <blockquote>
                <p>"The world's most valuable resource is no longer oil, but data."</p>
                <cite>— The Economist, 2017</cite>
            </blockquote>

            <h2>Roadmap Belajar AI untuk Pemula</h2>
            <h3>Bulan 1-2: Fondasi Programming</h3>
            <ul>
                <li>Python basics</li>
                <li>Git version control</li>
                <li>Jupyter Notebook</li>
                <li>Pandas dan NumPy</li>
            </ul>

            <h3>Bulan 3-4: Machine Learning Dasar</h3>
            <ul>
                <li>Descriptive statistics</li>
                <li>Supervised learning</li>
                <li>Unsupervised learning</li>
            </ul>

            <h2>Peluang Karier AI di Indonesia</h2>
            <p>Indonesia adalah pasar yang sangat menjanjikan untuk karier AI.</p>
            <figure>
                <table>
                    <thead>
                        <tr><th>Posisi</th><th>Junior</th><th>Mid</th><th>Senior</th></tr>
                    </thead>
                    <tbody>
                        <tr><td>Data Analyst</td><td>8-15 juta</td><td>15-25 juta</td><td>25-40 juta</td></tr>
                        <tr><td>Data Scientist</td><td>12-20 juta</td><td>20-35 juta</td><td>35-60 juta</td></tr>
                        <tr><td>ML Engineer</td><td>15-25 juta</td><td>25-45 juta</td><td>45-80 juta</td></tr>
                    </tbody>
                </table>
                <figcaption>*Estimasi gaji bulanan dalam Rupiah</figcaption>
            </figure>

            <h2>Kesimpulan</h2>
            <p>Membangun karier di AI membutuhkan komitmen dan pembelajaran berkelanjutan. Dengan roadmap yang jelas, Anda bisa mencapainya dalam 6-12 bulan.</p>
            <p><em>Tertarik untuk memulai? <a href="/apply">Daftar program kami</a> dan mulai transformasi karier Anda.</em></p>
        `
    };

    const relatedPosts = [
        { id: 2, title: "SvelteKit vs Next.js: Mana yang Lebih Cocok?", category: "Web Development", image: "https://images.unsplash.com/photo-1555066931-4365d14bab8c?w=400&h=250&fit=crop", date: "12 Jan 2025" },
        { id: 3, title: "Machine Learning untuk Pemula", category: "Machine Learning", image: "https://images.unsplash.com/photo-1515879218367-8466d910aaa4?w=400&h=250&fit=crop", date: "10 Jan 2025" },
        { id: 6, title: "Prompt Engineering: Seni Berkomunikasi dengan AI", category: "AI Tools", image: "https://images.unsplash.com/photo-1676299081847-824916de030a?w=400&h=250&fit=crop", date: "3 Jan 2025" }
    ];

    const tableOfContents = [
        { id: "landscape", title: "Memahami Lanskap AI" },
        { id: "skills", title: "Skill Fundamental" },
        { id: "roadmap", title: "Roadmap Belajar" },
        { id: "peluang", title: "Peluang Karier" },
        { id: "kesimpulan", title: "Kesimpulan" }
    ];
</script>

<svelte:head>
    <title>{article.title} | Neuversity Blog</title>
    <meta name="description" content={article.excerpt} />
</svelte:head>

<!-- Hero -->
<section class="relative">
    <div class="absolute inset-0 h-[50vh] overflow-hidden">
        <img src={article.image} alt={article.title} class="w-full h-full object-cover" />
        <div class="absolute inset-0 bg-gradient-to-b from-slate-950/60 via-slate-950/80 to-slate-950"></div>
    </div>
    
    <div class="relative max-w-4xl mx-auto px-6 pt-16 pb-12">
        <nav class="flex items-center gap-2 text-sm mb-8">
            <a href="/" class="text-slate-400 hover:text-emerald-400">Home</a>
            <svg class="w-4 h-4 text-slate-600" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7" /></svg>
            <a href="/blog" class="text-slate-400 hover:text-emerald-400">Blog</a>
            <svg class="w-4 h-4 text-slate-600" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7" /></svg>
            <span class="text-emerald-400">{article.category}</span>
        </nav>

        <div class="flex items-center gap-4 mb-6">
            <span class="px-4 py-1.5 bg-emerald-500 text-slate-950 text-sm font-semibold rounded-full">{article.category}</span>
            <span class="text-slate-400 text-sm">{article.date}</span>
            <span class="text-slate-600">•</span>
            <span class="text-slate-400 text-sm">{article.readTime}</span>
        </div>

        <h1 class="text-3xl md:text-4xl lg:text-5xl font-bold text-white leading-tight mb-6">{article.title}</h1>
        <p class="text-xl text-slate-300 mb-8">{article.excerpt}</p>

        <div class="flex flex-wrap gap-2 mb-8">
            {#each article.tags as tag}
                <a href="/blog?tag={tag}" class="px-3 py-1 bg-slate-800/50 text-slate-400 text-sm rounded-full hover:bg-emerald-500/20 hover:text-emerald-400">#{tag}</a>
            {/each}
        </div>

        <div class="flex items-center gap-4 p-4 bg-slate-900/50 backdrop-blur-sm rounded-2xl border border-emerald-500/10">
            <img src={article.author.avatar} alt={article.author.name} class="w-14 h-14 rounded-xl object-cover ring-2 ring-emerald-500/20" />
            <div class="flex-1">
                <h3 class="text-white font-semibold">{article.author.name}</h3>
                <p class="text-emerald-400 text-sm">{article.author.role}</p>
            </div>
        </div>
    </div>
</section>

<!-- Content -->
<section class="max-w-7xl mx-auto px-6 py-12">
    <div class="grid lg:grid-cols-4 gap-12">
        <aside class="hidden lg:block lg:col-span-1">
            <div class="sticky top-28 space-y-6">
                <div class="bg-slate-900/50 rounded-2xl p-6 border border-emerald-500/10">
                    <h3 class="text-sm font-semibold text-white mb-4">Daftar Isi</h3>
                    <nav class="space-y-2">
                        {#each tableOfContents as item}
                            <a href="#{item.id}" class="block text-sm text-slate-400 hover:text-emerald-400 py-1 pl-4 border-l-2 border-slate-800 hover:border-emerald-400">{item.title}</a>
                        {/each}
                    </nav>
                </div>
                <div class="bg-slate-900/50 rounded-2xl p-6 border border-emerald-500/10">
                    <h3 class="text-sm font-semibold text-white mb-4">Bagikan</h3>
                    <div class="flex gap-2">
                        <button class="flex-1 p-3 bg-slate-800 hover:bg-emerald-500 rounded-lg text-slate-400 hover:text-slate-950 transition-all">
                            <svg class="w-5 h-5 mx-auto" fill="currentColor" viewBox="0 0 24 24"><path d="M24 4.557c-.883.392-1.832.656-2.828.775 1.017-.609 1.798-1.574 2.165-2.724-.951.564-2.005.974-3.127 1.195-.897-.957-2.178-1.555-3.594-1.555-3.179 0-5.515 2.966-4.797 6.045-4.091-.205-7.719-2.165-10.148-5.144-1.29 2.213-.669 5.108 1.523 6.574-.806-.026-1.566-.247-2.229-.616-.054 2.281 1.581 4.415 3.949 4.89-.693.188-1.452.232-2.224.084.626 1.956 2.444 3.379 4.6 3.419-2.07 1.623-4.678 2.348-7.29 2.04 2.179 1.397 4.768 2.212 7.548 2.212 9.142 0 14.307-7.721 13.995-14.646.962-.695 1.797-1.562 2.457-2.549z"/></svg>
                        </button>
                        <button class="flex-1 p-3 bg-slate-800 hover:bg-emerald-500 rounded-lg text-slate-400 hover:text-slate-950 transition-all">
                            <svg class="w-5 h-5 mx-auto" fill="currentColor" viewBox="0 0 24 24"><path d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z"/></svg>
                        </button>
                    </div>
                </div>
            </div>
        </aside>

        <article class="lg:col-span-3">
            <div class="prose prose-lg prose-invert prose-emerald max-w-none">
                {@html article.content}
            </div>

            <div class="mt-12 p-8 bg-slate-900/50 rounded-2xl border border-emerald-500/10">
                <div class="flex items-start gap-6">
                    <img src={article.author.avatar} alt={article.author.name} class="w-20 h-20 rounded-2xl object-cover" />
                    <div>
                        <h3 class="text-xl font-bold text-white mb-1">Tentang {article.author.name}</h3>
                        <p class="text-emerald-400 text-sm mb-3">{article.author.role}</p>
                        <p class="text-slate-400">{article.author.bio}</p>
                    </div>
                </div>
            </div>
        </article>
    </div>
</section>

<!-- Related -->
<section class="max-w-7xl mx-auto px-6 py-12 border-t border-emerald-500/10">
    <h2 class="text-2xl font-bold text-white mb-8">Artikel Terkait</h2>
    <div class="grid md:grid-cols-3 gap-8">
        {#each relatedPosts as post}
            <article class="group bg-slate-900/50 rounded-2xl overflow-hidden border border-emerald-500/10 hover:border-emerald-500/30 transition-all">
                <div class="relative h-40 overflow-hidden">
                    <img src={post.image} alt={post.title} class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500" />
                    <div class="absolute inset-0 bg-gradient-to-t from-slate-900/80 to-transparent"></div>
                    <span class="absolute bottom-3 left-3 px-2 py-1 bg-emerald-500/90 text-slate-950 text-xs font-semibold rounded">{post.category}</span>
                </div>
                <div class="p-5">
                    <p class="text-slate-500 text-xs mb-2">{post.date}</p>
                    <h3 class="text-white font-semibold group-hover:text-emerald-400 transition-colors">
                        <a href="/blog/{post.id}">{post.title}</a>
                    </h3>
                </div>
            </article>
        {/each}
    </div>
</section>

<style>
    .prose { color: #94a3b8; }
    .prose h2 { color: white; font-size: 1.75rem; font-weight: 700; margin-top: 2.5rem; margin-bottom: 1rem; padding-bottom: 0.5rem; border-bottom: 1px solid rgba(16, 185, 129, 0.2); }
    .prose h3 { color: white; font-size: 1.25rem; font-weight: 600; margin-top: 2rem; margin-bottom: 0.75rem; }
    .prose p { margin-bottom: 1.25rem; line-height: 1.8; }
    .prose .lead { font-size: 1.25rem; color: #cbd5e1; line-height: 1.7; margin-bottom: 2rem; }
    .prose ul, .prose ol { margin: 1.5rem 0; padding-left: 1.5rem; }
    .prose li { margin-bottom: 0.5rem; line-height: 1.7; }
    .prose li strong { color: #10b981; }
    .prose blockquote { border-left: 4px solid #10b981; padding: 1rem 1.5rem; margin: 2rem 0; background: rgba(16, 185, 129, 0.05); border-radius: 0 1rem 1rem 0; }
    .prose blockquote p { font-size: 1.125rem; font-style: italic; color: #e2e8f0; margin-bottom: 0.5rem; }
    .prose blockquote cite { font-size: 0.875rem; color: #64748b; font-style: normal; }
    .prose pre { background: #0f172a; border: 1px solid rgba(16, 185, 129, 0.2); border-radius: 1rem; padding: 1.5rem; overflow-x: auto; margin: 1.5rem 0; }
    .prose code { font-family: 'Space Mono', monospace; font-size: 0.875rem; color: #10b981; }
    .prose pre code { color: #e2e8f0; }
    .prose a { color: #10b981; text-decoration: underline; }
    .prose table { width: 100%; margin: 2rem 0; border-collapse: collapse; }
    .prose th { background: rgba(16, 185, 129, 0.1); color: white; font-weight: 600; text-align: left; padding: 1rem; border-bottom: 2px solid rgba(16, 185, 129, 0.3); }
    .prose td { padding: 1rem; border-bottom: 1px solid #1e293b; }
    .prose figcaption { font-size: 0.875rem; color: #64748b; text-align: center; margin-top: 0.75rem; }
</style>