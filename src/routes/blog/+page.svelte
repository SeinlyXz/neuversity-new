<script>
    // Static blog data
    const featuredPost = {
        id: 1,
        title: "Membangun Karier di Era AI: Panduan Lengkap untuk Pemula",
        excerpt: "Pelajari bagaimana artificial intelligence mengubah landscape karier teknologi dan bagaimana Anda bisa mempersiapkan diri untuk masa depan yang penuh dengan peluang.",
        category: "AI & Career",
        author: {
            name: "Andi Pratama",
            avatar: "https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?w=100&h=100&fit=crop&crop=face",
            role: "Head of AI Program"
        },
        date: "15 Januari 2025",
        readTime: "8 min read",
        image: "https://images.unsplash.com/photo-1677442136019-21780ecad995?w=1200&h=600&fit=crop",
        tags: ["AI", "Career", "Technology"]
    };

    const posts = [
        {
            id: 2,
            title: "SvelteKit vs Next.js: Mana yang Lebih Cocok untuk Proyekmu?",
            excerpt: "Perbandingan mendalam antara dua framework modern untuk membantu Anda membuat keputusan yang tepat.",
            category: "Web Development",
            author: {
                name: "Dewi Sartika",
                avatar: "https://images.unsplash.com/photo-1494790108377-be9c29b29330?w=100&h=100&fit=crop&crop=face",
                role: "Senior Developer"
            },
            date: "12 Januari 2025",
            readTime: "6 min read",
            image: "https://images.unsplash.com/photo-1555066931-4365d14bab8c?w=600&h=400&fit=crop",
            tags: ["SvelteKit", "Next.js", "JavaScript"]
        },
        {
            id: 3,
            title: "Machine Learning untuk Pemula: Dari Nol Hingga Model Pertama",
            excerpt: "Tutorial step-by-step membangun model machine learning pertama Anda menggunakan Python dan scikit-learn.",
            category: "Machine Learning",
            author: {
                name: "Budi Santoso",
                avatar: "https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?w=100&h=100&fit=crop&crop=face",
                role: "ML Engineer"
            },
            date: "10 Januari 2025",
            readTime: "12 min read",
            image: "https://images.unsplash.com/photo-1515879218367-8466d910aaa4?w=600&h=400&fit=crop",
            tags: ["Python", "Machine Learning", "Tutorial"]
        },
        {
            id: 4,
            title: "Design System: Fondasi UI yang Konsisten dan Scalable",
            excerpt: "Bagaimana membangun design system yang efektif untuk tim development Anda.",
            category: "UI/UX Design",
            author: {
                name: "Citra Permata",
                avatar: "https://images.unsplash.com/photo-1438761681033-6461ffad8d80?w=100&h=100&fit=crop&crop=face",
                role: "Lead Designer"
            },
            date: "8 Januari 2025",
            readTime: "7 min read",
            image: "https://images.unsplash.com/photo-1561070791-2526d30994b5?w=600&h=400&fit=crop",
            tags: ["Design System", "UI/UX", "Figma"]
        },
        {
            id: 5,
            title: "PostgreSQL vs MongoDB: Kapan Menggunakan SQL vs NoSQL",
            excerpt: "Panduan praktis memilih database yang tepat berdasarkan kebutuhan aplikasi Anda.",
            category: "Database",
            author: {
                name: "Eko Widodo",
                avatar: "https://images.unsplash.com/photo-1500648767791-00dcc994a43e?w=100&h=100&fit=crop&crop=face",
                role: "Database Architect"
            },
            date: "5 Januari 2025",
            readTime: "9 min read",
            image: "https://images.unsplash.com/photo-1544383835-bda2bc66a55d?w=600&h=400&fit=crop",
            tags: ["PostgreSQL", "MongoDB", "Database"]
        },
        {
            id: 6,
            title: "Prompt Engineering: Seni Berkomunikasi dengan AI",
            excerpt: "Tips dan trik untuk mendapatkan hasil maksimal dari ChatGPT, Claude, dan model AI lainnya.",
            category: "AI Tools",
            author: {
                name: "Fitri Handayani",
                avatar: "https://images.unsplash.com/photo-1534528741775-53994a69daeb?w=100&h=100&fit=crop&crop=face",
                role: "AI Specialist"
            },
            date: "3 Januari 2025",
            readTime: "5 min read",
            image: "https://images.unsplash.com/photo-1676299081847-824916de030a?w=600&h=400&fit=crop",
            tags: ["Prompt Engineering", "ChatGPT", "AI"]
        }
    ];

    const categories = [
        { name: "Semua", count: 24, active: true },
        { name: "AI & Machine Learning", count: 8 },
        { name: "Web Development", count: 6 },
        { name: "Mobile Development", count: 4 },
        { name: "UI/UX Design", count: 3 },
        { name: "Career Tips", count: 3 }
    ];

    const popularTags = [
        "JavaScript", "Python", "React", "AI", "Machine Learning", 
        "SvelteKit", "TypeScript", "Node.js", "TailwindCSS", "Career"
    ];
</script>

<svelte:head>
    <title>Blog | Neuversity - Sekolah Coding & AI Yogyakarta</title>
    <meta name="description" content="Artikel, tutorial, dan insight terbaru seputar coding, AI, dan teknologi dari Neuversity." />
</svelte:head>

<!-- Hero Section -->
<section class="relative overflow-hidden">
    <!-- Background Elements -->
    <div class="absolute inset-0 bg-gradient-to-b from-emerald-500/5 via-transparent to-transparent"></div>
    <div class="absolute top-0 left-1/4 w-96 h-96 bg-emerald-500/10 rounded-full blur-3xl"></div>
    <div class="absolute top-20 right-1/4 w-64 h-64 bg-emerald-400/5 rounded-full blur-2xl"></div>
    
    <!-- Grid Pattern -->
    <div class="absolute inset-0 opacity-[0.02]" style="background-image: url(&quot;data:image/svg+xml,%3Csvg width='60' height='60' viewBox='0 0 60 60' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='none' fill-rule='evenodd'%3E%3Cg fill='%2310b981' fill-opacity='1'%3E%3Cpath d='M36 34v-4h-2v4h-4v2h4v4h2v-4h4v-2h-4zm0-30V0h-2v4h-4v2h4v4h2V6h4V4h-4zM6 34v-4H4v4H0v2h4v4h2v-4h4v-2H6zM6 4V0H4v4H0v2h4v4h2V6h4V4H6z'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E&quot;);"></div>
    
    <div class="relative max-w-7xl mx-auto px-6 pt-16 pb-12">
        <div class="text-center max-w-3xl mx-auto">
            <div class="inline-flex items-center gap-2 px-4 py-2 bg-emerald-500/10 border border-emerald-500/20 rounded-full mb-6">
                <span class="w-2 h-2 bg-emerald-400 rounded-full animate-pulse"></span>
                <span class="text-emerald-400 text-sm font-medium">Neuversity Blog</span>
            </div>
            
            <h1 class="text-4xl md:text-5xl lg:text-6xl font-bold mb-6 leading-tight">
                <span class="text-white">Insight & Tutorial</span><br/>
                <span class="bg-gradient-to-r from-emerald-400 to-emerald-600 bg-clip-text text-transparent">Coding & AI</span>
            </h1>
            
            <p class="text-slate-400 text-lg md:text-xl max-w-2xl mx-auto mb-10">
                Pelajari teknologi terkini, tips karier, dan best practices dari para praktisi dan mentor Neuversity.
            </p>

            <!-- Search Bar -->
            <div class="relative max-w-xl mx-auto">
                <input 
                    type="text" 
                    placeholder="Cari artikel, tutorial, atau topik..."
                    class="w-full px-6 py-4 pl-14 bg-slate-900/50 border border-emerald-500/20 rounded-2xl text-white placeholder-slate-500 focus:outline-none focus:border-emerald-500/50 focus:ring-2 focus:ring-emerald-500/20 transition-all"
                />
                <svg class="absolute left-5 top-1/2 -translate-y-1/2 w-5 h-5 text-slate-500" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z" />
                </svg>
            </div>
        </div>
    </div>
</section>

<!-- Featured Post -->
<section class="max-w-7xl mx-auto px-6 py-8">
    <div class="relative group">
        <div class="absolute -inset-0.5 bg-gradient-to-r from-emerald-500 to-emerald-600 rounded-3xl opacity-20 group-hover:opacity-30 blur transition-opacity duration-300"></div>
        <article class="relative bg-slate-900/80 backdrop-blur-sm rounded-3xl overflow-hidden border border-emerald-500/10">
            <div class="grid md:grid-cols-2 gap-0">
                <!-- Image -->
                <div class="relative h-64 md:h-auto overflow-hidden">
                    <img 
                        src={featuredPost.image} 
                        alt={featuredPost.title}
                        class="absolute inset-0 w-full h-full object-cover transform group-hover:scale-105 transition-transform duration-700"
                    />
                    <div class="absolute inset-0 bg-gradient-to-r from-transparent to-slate-900/50 md:bg-gradient-to-l md:from-slate-900 md:to-transparent"></div>
                    <span class="absolute top-6 left-6 px-4 py-1.5 bg-emerald-500 text-slate-950 text-xs font-bold rounded-full uppercase tracking-wide">
                        Featured
                    </span>
                </div>
                
                <!-- Content -->
                <div class="p-8 md:p-12 flex flex-col justify-center">
                    <span class="text-emerald-400 text-sm font-medium mb-3">{featuredPost.category}</span>
                    <h2 class="text-2xl md:text-3xl font-bold text-white mb-4 leading-tight group-hover:text-emerald-400 transition-colors">
                        <a href="/blog/{featuredPost.id}">{featuredPost.title}</a>
                    </h2>
                    <p class="text-slate-400 mb-6 line-clamp-2">{featuredPost.excerpt}</p>
                    
                    <!-- Tags -->
                    <div class="flex flex-wrap gap-2 mb-6">
                        {#each featuredPost.tags as tag}
                            <span class="px-3 py-1 bg-slate-800 text-slate-400 text-xs rounded-full hover:bg-emerald-500/20 hover:text-emerald-400 transition-colors cursor-pointer">
                                #{tag}
                            </span>
                        {/each}
                    </div>
                    
                    <!-- Author & Meta -->
                    <div class="flex items-center justify-between pt-6 border-t border-slate-800">
                        <div class="flex items-center gap-3">
                            <img 
                                src={featuredPost.author.avatar} 
                                alt={featuredPost.author.name}
                                class="w-10 h-10 rounded-full object-cover ring-2 ring-emerald-500/20"
                            />
                            <div>
                                <p class="text-white text-sm font-medium">{featuredPost.author.name}</p>
                                <p class="text-slate-500 text-xs">{featuredPost.author.role}</p>
                            </div>
                        </div>
                        <div class="text-right">
                            <p class="text-slate-400 text-sm">{featuredPost.date}</p>
                            <p class="text-slate-500 text-xs">{featuredPost.readTime}</p>
                        </div>
                    </div>
                </div>
            </div>
        </article>
    </div>
</section>

<!-- Main Content -->
<section class="max-w-7xl mx-auto px-6 py-12">
    <div class="grid lg:grid-cols-4 gap-12">
        <!-- Posts Grid -->
        <div class="lg:col-span-3">
            <div class="flex items-center justify-between mb-8">
                <h2 class="text-2xl font-bold text-white">Artikel Terbaru</h2>
                <select class="px-4 py-2 bg-slate-900 border border-emerald-500/20 rounded-lg text-slate-400 text-sm focus:outline-none focus:border-emerald-500/50">
                    <option>Terbaru</option>
                    <option>Populer</option>
                    <option>Trending</option>
                </select>
            </div>

            <div class="grid md:grid-cols-2 gap-8">
                {#each posts as post}
                    <article class="group bg-slate-900/50 rounded-2xl overflow-hidden border border-emerald-500/10 hover:border-emerald-500/30 transition-all duration-300 hover:shadow-lg hover:shadow-emerald-500/5">
                        <!-- Image -->
                        <div class="relative h-48 overflow-hidden">
                            <img 
                                src={post.image} 
                                alt={post.title}
                                class="w-full h-full object-cover transform group-hover:scale-105 transition-transform duration-500"
                            />
                            <div class="absolute inset-0 bg-gradient-to-t from-slate-900/80 to-transparent"></div>
                            <span class="absolute bottom-4 left-4 px-3 py-1 bg-emerald-500/90 text-slate-950 text-xs font-semibold rounded-full">
                                {post.category}
                            </span>
                        </div>
                        
                        <!-- Content -->
                        <div class="p-6">
                            <h3 class="text-lg font-bold text-white mb-3 line-clamp-2 group-hover:text-emerald-400 transition-colors">
                                <a href="/blog/{post.id}">{post.title}</a>
                            </h3>
                            <p class="text-slate-400 text-sm mb-4 line-clamp-2">{post.excerpt}</p>
                            
                            <!-- Tags -->
                            <div class="flex flex-wrap gap-2 mb-4">
                                {#each post.tags.slice(0, 2) as tag}
                                    <span class="px-2 py-0.5 bg-slate-800 text-slate-500 text-xs rounded">
                                        {tag}
                                    </span>
                                {/each}
                            </div>
                            
                            <!-- Author & Meta -->
                            <div class="flex items-center justify-between pt-4 border-t border-slate-800">
                                <div class="flex items-center gap-2">
                                    <img 
                                        src={post.author.avatar} 
                                        alt={post.author.name}
                                        class="w-8 h-8 rounded-full object-cover"
                                    />
                                    <span class="text-slate-400 text-sm">{post.author.name}</span>
                                </div>
                                <span class="text-slate-500 text-xs">{post.readTime}</span>
                            </div>
                        </div>
                    </article>
                {/each}
            </div>

            <!-- Pagination -->
            <div class="flex items-center justify-center gap-2 mt-12">
                <button class="p-2 text-slate-400 hover:text-emerald-400 transition-colors">
                    <svg class="w-5 h-5" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 19l-7-7 7-7" />
                    </svg>
                </button>
                <button class="w-10 h-10 bg-emerald-500 text-slate-950 font-semibold rounded-lg">1</button>
                <button class="w-10 h-10 text-slate-400 hover:bg-slate-800 rounded-lg transition-colors">2</button>
                <button class="w-10 h-10 text-slate-400 hover:bg-slate-800 rounded-lg transition-colors">3</button>
                <span class="text-slate-500">...</span>
                <button class="w-10 h-10 text-slate-400 hover:bg-slate-800 rounded-lg transition-colors">12</button>
                <button class="p-2 text-slate-400 hover:text-emerald-400 transition-colors">
                    <svg class="w-5 h-5" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7" />
                    </svg>
                </button>
            </div>
        </div>

        <!-- Sidebar -->
        <aside class="lg:col-span-1 space-y-8">
            <!-- Categories -->
            <div class="bg-slate-900/50 rounded-2xl p-6 border border-emerald-500/10">
                <h3 class="text-lg font-bold text-white mb-4 flex items-center gap-2">
                    <svg class="w-5 h-5 text-emerald-400" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h7" />
                    </svg>
                    Kategori
                </h3>
                <ul class="space-y-2">
                    {#each categories as category}
                        <li>
                            <a 
                                href="#" 
                                class="flex items-center justify-between p-3 rounded-lg transition-all duration-200 {category.active ? 'bg-emerald-500/10 text-emerald-400' : 'text-slate-400 hover:bg-slate-800 hover:text-white'}"
                            >
                                <span class="text-sm">{category.name}</span>
                                <span class="text-xs px-2 py-0.5 bg-slate-800 rounded-full {category.active ? 'text-emerald-400' : 'text-slate-500'}">
                                    {category.count}
                                </span>
                            </a>
                        </li>
                    {/each}
                </ul>
            </div>

            <!-- Popular Tags -->
            <div class="bg-slate-900/50 rounded-2xl p-6 border border-emerald-500/10">
                <h3 class="text-lg font-bold text-white mb-4 flex items-center gap-2">
                    <svg class="w-5 h-5 text-emerald-400" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M7 7h.01M7 3h5c.512 0 1.024.195 1.414.586l7 7a2 2 0 010 2.828l-7 7a2 2 0 01-2.828 0l-7-7A1.994 1.994 0 013 12V7a4 4 0 014-4z" />
                    </svg>
                    Tags Populer
                </h3>
                <div class="flex flex-wrap gap-2">
                    {#each popularTags as tag}
                        <a 
                            href="#" 
                            class="px-3 py-1.5 bg-slate-800 text-slate-400 text-sm rounded-lg hover:bg-emerald-500/20 hover:text-emerald-400 transition-all duration-200"
                        >
                            #{tag}
                        </a>
                    {/each}
                </div>
            </div>

            <!-- Newsletter -->
            <div class="bg-gradient-to-br from-emerald-500/20 to-emerald-600/10 rounded-2xl p-6 border border-emerald-500/20">
                <div class="w-12 h-12 bg-emerald-500/20 rounded-xl flex items-center justify-center mb-4">
                    <svg class="w-6 h-6 text-emerald-400" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" />
                    </svg>
                </div>
                <h3 class="text-lg font-bold text-white mb-2">Newsletter</h3>
                <p class="text-slate-400 text-sm mb-4">Dapatkan artikel terbaru langsung ke inbox Anda.</p>
                <form class="space-y-3">
                    <input 
                        type="email" 
                        placeholder="Email Anda"
                        class="w-full px-4 py-3 bg-slate-900/50 border border-emerald-500/20 rounded-xl text-white text-sm placeholder-slate-500 focus:outline-none focus:border-emerald-500/50"
                    />
                    <button type="submit" class="w-full px-4 py-3 bg-emerald-500 hover:bg-emerald-400 text-slate-950 font-semibold text-sm rounded-xl transition-colors">
                        Subscribe
                    </button>
                </form>
            </div>

            <!-- CTA Banner -->
            <div class="relative overflow-hidden rounded-2xl p-6 bg-slate-900">
                <div class="absolute inset-0 bg-gradient-to-br from-emerald-500/10 to-transparent"></div>
                <div class="absolute top-0 right-0 w-32 h-32 bg-emerald-500/20 rounded-full blur-3xl"></div>
                <div class="relative">
                    <span class="inline-block px-3 py-1 bg-emerald-500/20 text-emerald-400 text-xs font-medium rounded-full mb-4">
                        Pendaftaran Dibuka
                    </span>
                    <h3 class="text-xl font-bold text-white mb-2">Batch Januari 2025</h3>
                    <p class="text-slate-400 text-sm mb-4">Mulai perjalanan coding Anda bersama mentor berpengalaman.</p>
                    <a href="/apply" class="inline-flex items-center gap-2 text-emerald-400 text-sm font-medium hover:gap-3 transition-all">
                        Daftar Sekarang
                        <svg class="w-4 h-4" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 8l4 4m0 0l-4 4m4-4H3" />
                        </svg>
                    </a>
                </div>
            </div>
        </aside>
    </div>
</section>

<style>
    .line-clamp-2 {
        display: -webkit-box;
        -webkit-line-clamp: 2;
        -webkit-box-orient: vertical;
        overflow: hidden;
    }
</style>