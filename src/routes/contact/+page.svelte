<script>
  import { fade, fly, scale } from 'svelte/transition';
  import { quintOut } from 'svelte/easing';
  
  let formData = {
    name: '',
    email: '',
    phone: '',
    subject: '',
    message: ''
  };
  
  let errors = {};
  let isSubmitting = false;
  let showSuccess = false;
  let focusedField = null;
  
  const contactInfo = [
    {
      icon: '📧',
      title: 'Email',
      value: 'hello@yourcompany.com',
      link: 'mailto:hello@yourcompany.com'
    },
    {
      icon: '📱',
      title: 'Phone',
      value: '+62 812 3456 7890',
      link: 'tel:+6281234567890'
    },
    {
      icon: '📍',
      title: 'Address',
      value: 'Jl. Contoh No. 123, Bandung, West Java 40132',
      link: 'https://maps.google.com'
    }
  ];
  
  const socialMedia = [
    { name: 'LinkedIn', icon: '💼', url: 'https://linkedin.com' },
    { name: 'Twitter', icon: '🐦', url: 'https://twitter.com' },
    { name: 'Instagram', icon: '📸', url: 'https://instagram.com' },
    { name: 'Facebook', icon: '👥', url: 'https://facebook.com' }
  ];
  
  function validateEmail(email) {
    return /^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email);
  }
  
  function validatePhone(phone) {
    return /^[\d\s+()-]{10,}$/.test(phone);
  }
  
  function validateForm() {
    const newErrors = {};
    
    if (!formData.name.trim()) {
      newErrors.name = 'Name is required';
    }
    
    if (!formData.email.trim()) {
      newErrors.email = 'Email is required';
    } else if (!validateEmail(formData.email)) {
      newErrors.email = 'Please enter a valid email';
    }
    
    if (formData.phone && !validatePhone(formData.phone)) {
      newErrors.phone = 'Please enter a valid phone number';
    }
    
    if (!formData.subject.trim()) {
      newErrors.subject = 'Subject is required';
    }
    
    if (!formData.message.trim()) {
      newErrors.message = 'Message is required';
    } else if (formData.message.trim().length < 10) {
      newErrors.message = 'Message must be at least 10 characters';
    }
    
    errors = newErrors;
    return Object.keys(newErrors).length === 0;
  }
  
  async function handleSubmit(e) {
    e.preventDefault();
    
    if (!validateForm()) {
      return;
    }
    
    isSubmitting = true;
    
    // Simulate API call
    await new Promise(resolve => setTimeout(resolve, 1500));
    
    isSubmitting = false;
    showSuccess = true;
    
    // Reset form
    formData = {
      name: '',
      email: '',
      phone: '',
      subject: '',
      message: ''
    };
    
    setTimeout(() => {
      showSuccess = false;
    }, 5000);
  }
  
  function handleInput(field) {
    if (errors[field]) {
      errors = { ...errors, [field]: undefined };
    }
  }
</script>

<div class="min-h-screen bg-gradient-to-br from-slate-50 to-slate-100 py-12 px-4 sm:px-6 lg:px-8">
  <div class="max-w-7xl mx-auto">
    <!-- Header -->
    <div class="text-center mb-16" in:fade={{ duration: 600 }}>
      <h1 class="text-5xl font-bold text-slate-900 mb-4">Get In Touch</h1>
      <p class="text-xl text-slate-600 max-w-2xl mx-auto">
        Have a question or want to work together? We'd love to hear from you.
      </p>
    </div>

    <div class="grid lg:grid-cols-5 gap-8">
      <!-- Contact Info Sidebar -->
      <div class="lg:col-span-2 space-y-6">
        <!-- Contact Cards -->
        {#each contactInfo as info, i}
          <a
            href={info.link}
            target="_blank"
            rel="noopener noreferrer"
            class="block bg-white rounded-2xl p-6 shadow-lg hover:shadow-xl transition-all duration-300 hover:-translate-y-1 border border-slate-200"
            in:fly={{ y: 20, duration: 500, delay: i * 100 }}
          >
            <div class="flex items-start gap-4">
              <div class="text-4xl">{info.icon}</div>
              <div class="flex-1">
                <h3 class="font-semibold text-slate-900 mb-1">{info.title}</h3>
                <p class="text-slate-600 text-sm leading-relaxed">{info.value}</p>
              </div>
            </div>
          </a>
        {/each}

        <!-- Social Media -->
        <div 
          class="bg-white rounded-2xl p-6 shadow-lg border border-slate-200"
          in:fly={{ y: 20, duration: 500, delay: 300 }}
        >
          <h3 class="font-semibold text-slate-900 mb-4">Follow Us</h3>
          <div class="flex gap-3">
            {#each socialMedia as social}
              <a
                href={social.url}
                target="_blank"
                rel="noopener noreferrer"
                class="w-12 h-12 bg-slate-100 rounded-xl flex items-center justify-center text-2xl hover:bg-slate-900 hover:scale-110 transition-all duration-300 group"
                title={social.name}
              >
                <span class="group-hover:scale-125 transition-transform duration-300">
                  {social.icon}
                </span>
              </a>
            {/each}
          </div>
        </div>

        <!-- Business Hours -->
        <div 
          class="bg-gradient-to-br from-slate-900 to-slate-800 rounded-2xl p-6 shadow-lg text-white"
          in:fly={{ y: 20, duration: 500, delay: 400 }}
        >
          <h3 class="font-semibold mb-3">Business Hours</h3>
          <div class="space-y-2 text-sm text-slate-300">
            <div class="flex justify-between">
              <span>Monday - Friday</span>
              <span>9:00 - 18:00</span>
            </div>
            <div class="flex justify-between">
              <span>Saturday</span>
              <span>10:00 - 14:00</span>
            </div>
            <div class="flex justify-between">
              <span>Sunday</span>
              <span>Closed</span>
            </div>
          </div>
        </div>
      </div>

      <!-- Contact Form -->
      <div class="lg:col-span-3">
        <div 
          class="bg-white rounded-2xl p-8 shadow-xl border border-slate-200"
          in:fly={{ x: 20, duration: 600, delay: 200 }}
        >
          <h2 class="text-2xl font-bold text-slate-900 mb-6">Send us a message</h2>
          
          <form on:submit={handleSubmit} class="space-y-6">
            <!-- Name -->
            <div>
              <label for="name" class="block text-sm font-medium text-slate-700 mb-2">
                Full Name *
              </label>
              <input
                id="name"
                type="text"
                bind:value={formData.name}
                on:input={() => handleInput('name')}
                on:focus={() => focusedField = 'name'}
                on:blur={() => focusedField = null}
                class="w-full px-4 py-3 rounded-xl border-2 transition-all duration-300 outline-none {errors.name ? 'border-red-300 bg-red-50' : focusedField === 'name' ? 'border-slate-900 bg-white' : 'border-slate-200 bg-slate-50'}"
                placeholder="John Doe"
              />
              {#if errors.name}
                <p class="mt-1 text-sm text-red-600" in:scale={{ duration: 200 }}>{errors.name}</p>
              {/if}
            </div>

            <!-- Email & Phone -->
            <div class="grid md:grid-cols-2 gap-6">
              <div>
                <label for="email" class="block text-sm font-medium text-slate-700 mb-2">
                  Email Address *
                </label>
                <input
                  id="email"
                  type="email"
                  bind:value={formData.email}
                  on:input={() => handleInput('email')}
                  on:focus={() => focusedField = 'email'}
                  on:blur={() => focusedField = null}
                  class="w-full px-4 py-3 rounded-xl border-2 transition-all duration-300 outline-none {errors.email ? 'border-red-300 bg-red-50' : focusedField === 'email' ? 'border-slate-900 bg-white' : 'border-slate-200 bg-slate-50'}"
                  placeholder="john@example.com"
                />
                {#if errors.email}
                  <p class="mt-1 text-sm text-red-600" in:scale={{ duration: 200 }}>{errors.email}</p>
                {/if}
              </div>

              <div>
                <label for="phone" class="block text-sm font-medium text-slate-700 mb-2">
                  Phone Number
                </label>
                <input
                  id="phone"
                  type="tel"
                  bind:value={formData.phone}
                  on:input={() => handleInput('phone')}
                  on:focus={() => focusedField = 'phone'}
                  on:blur={() => focusedField = null}
                  class="w-full px-4 py-3 rounded-xl border-2 transition-all duration-300 outline-none {errors.phone ? 'border-red-300 bg-red-50' : focusedField === 'phone' ? 'border-slate-900 bg-white' : 'border-slate-200 bg-slate-50'}"
                  placeholder="+62 812 3456 7890"
                />
                {#if errors.phone}
                  <p class="mt-1 text-sm text-red-600" in:scale={{ duration: 200 }}>{errors.phone}</p>
                {/if}
              </div>
            </div>

            <!-- Subject -->
            <div>
              <label for="subject" class="block text-sm font-medium text-slate-700 mb-2">
                Subject *
              </label>
              <input
                id="subject"
                type="text"
                bind:value={formData.subject}
                on:input={() => handleInput('subject')}
                on:focus={() => focusedField = 'subject'}
                on:blur={() => focusedField = null}
                class="w-full px-4 py-3 rounded-xl border-2 transition-all duration-300 outline-none {errors.subject ? 'border-red-300 bg-red-50' : focusedField === 'subject' ? 'border-slate-900 bg-white' : 'border-slate-200 bg-slate-50'}"
                placeholder="How can we help you?"
              />
              {#if errors.subject}
                <p class="mt-1 text-sm text-red-600" in:scale={{ duration: 200 }}>{errors.subject}</p>
              {/if}
            </div>

            <!-- Message -->
            <div>
              <label for="message" class="block text-sm font-medium text-slate-700 mb-2">
                Message *
              </label>
              <textarea
                id="message"
                bind:value={formData.message}
                on:input={() => handleInput('message')}
                on:focus={() => focusedField = 'message'}
                on:blur={() => focusedField = null}
                rows="6"
                class="w-full px-4 py-3 rounded-xl border-2 transition-all duration-300 outline-none resize-none {errors.message ? 'border-red-300 bg-red-50' : focusedField === 'message' ? 'border-slate-900 bg-white' : 'border-slate-200 bg-slate-50'}"
                placeholder="Tell us more about your inquiry..."
              ></textarea>
              {#if errors.message}
                <p class="mt-1 text-sm text-red-600" in:scale={{ duration: 200 }}>{errors.message}</p>
              {/if}
            </div>

            <!-- Submit Button -->
            <button
              type="submit"
              disabled={isSubmitting}
              class="w-full bg-slate-900 text-white py-4 rounded-xl font-semibold hover:bg-slate-800 transition-all duration-300 hover:shadow-lg hover:-translate-y-0.5 disabled:opacity-50 disabled:cursor-not-allowed disabled:hover:translate-y-0 flex items-center justify-center gap-2"
            >
              {#if isSubmitting}
                <span class="inline-block w-5 h-5 border-2 border-white border-t-transparent rounded-full animate-spin"></span>
                Sending...
              {:else}
                Send Message
                <span class="text-xl">→</span>
              {/if}
            </button>
          </form>
        </div>
      </div>
    </div>
  </div>
</div>

<!-- Success Toast -->
{#if showSuccess}
  <div 
    class="fixed bottom-8 right-8 bg-green-500 text-white px-6 py-4 rounded-xl shadow-2xl flex items-center gap-3"
    in:fly={{ y: 20, duration: 300 }}
    out:fly={{ y: 20, duration: 300 }}
  >
    <span class="text-2xl">✓</span>
    <div>
      <p class="font-semibold">Message sent successfully!</p>
      <p class="text-sm text-green-100">We'll get back to you soon.</p>
    </div>
  </div>
{/if}

<style>
  @keyframes spin {
    to { transform: rotate(360deg); }
  }
  
  .animate-spin {
    animation: spin 1s linear infinite;
  }
</style>