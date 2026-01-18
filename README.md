<!doctype html>
<html lang="en" class="h-full">
 <head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Assignment Hub</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <script src="/_sdk/element_sdk.js"></script>
  <link href="https://fonts.googleapis.com/css2?family=DM+Sans:wght@400;500;600;700&amp;display=swap" rel="stylesheet">
  <style>
    body {
      box-sizing: border-box;
    }
    * {
      font-family: 'DM Sans', sans-serif;
    }
    .assignment-card {
      transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
    }
    .assignment-card:hover {
      transform: translateY(-4px);
    }
    .modal-backdrop {
      animation: fadeIn 0.2s ease-out;
    }
    .modal-content {
      animation: slideUp 0.3s ease-out;
    }
    @keyframes fadeIn {
      from { opacity: 0; }
      to { opacity: 1; }
    }
    @keyframes slideUp {
      from { opacity: 0; transform: translateY(20px) scale(0.95); }
      to { opacity: 1; transform: translateY(0) scale(1); }
    }
  </style>
  <style>@view-transition { navigation: auto; }</style>
  <script src="/_sdk/data_sdk.js" type="text/javascript"></script>
 </head>
 <body class="h-full">
  <div id="app-wrapper" class="w-full h-full overflow-auto bg-gradient-to-br from-slate-900 via-purple-900 to-slate-900">
   <div class="w-full min-h-full px-4 py-12"><!-- Header -->
    <header class="text-center mb-12">
     <h1 id="page-title" class="text-4xl md:text-5xl font-bold text-white mb-3">Assignment Hub</h1>
     <p id="subtitle" class="text-purple-300 text-lg">Click on an assignment to view details</p>
    </header><!-- Assignment Grid -->
    <div class="max-w-4xl mx-auto grid gap-4 md:grid-cols-2 lg:grid-cols-3"><!-- Assignment 1 --> <button onclick="openModal(0)" class="assignment-card bg-gradient-to-br from-pink-400 to-pink-600 rounded-2xl p-6 text-left shadow-lg shadow-pink-500/20 hover:shadow-xl hover:shadow-pink-500/30">
      <div class="flex items-center gap-3 mb-4">
       <div class="w-12 h-12 bg-white/20 rounded-xl flex items-center justify-center"><span class="text-2xl">📝</span>
       </div><span class="bg-white/20 text-white text-xs font-medium px-3 py-1 rounded-full">Due: Week 2</span>
      </div><h3 class="text-xl font-bold text-white mb-2">Assignment 1</h3><p class="text-pink-100 text-sm">Research &amp; Analysis</p></button> <!-- Assignment 2 --> <button onclick="openModal(1)" class="assignment-card bg-gradient-to-br from-pink-500 to-rose-600 rounded-2xl p-6 text-left shadow-lg shadow-pink-500/20 hover:shadow-xl hover:shadow-pink-500/30">
      <div class="flex items-center gap-3 mb-4">
       <div class="w-12 h-12 bg-white/20 rounded-xl flex items-center justify-center"><span class="text-2xl">💻</span>
       </div><span class="bg-white/20 text-white text-xs font-medium px-3 py-1 rounded-full">Due: Week 4</span>
      </div><h3 class="text-xl font-bold text-white mb-2">Assignment 2</h3><p class="text-pink-100 text-sm">Programming Project</p></button> <!-- Assignment 3 --> <button onclick="openModal(2)" class="assignment-card bg-gradient-to-br from-rose-400 to-pink-600 rounded-2xl p-6 text-left shadow-lg shadow-rose-500/20 hover:shadow-xl hover:shadow-rose-500/30">
      <div class="flex items-center gap-3 mb-4">
       <div class="w-12 h-12 bg-white/20 rounded-xl flex items-center justify-center"><span class="text-2xl">📊</span>
       </div><span class="bg-white/20 text-white text-xs font-medium px-3 py-1 rounded-full">Due: Week 6</span>
      </div><h3 class="text-xl font-bold text-white mb-2">Assignment 3</h3><p class="text-rose-100 text-sm">Data Presentation</p></button> <!-- Assignment 4 --> <button onclick="openModal(3)" class="assignment-card bg-gradient-to-br from-pink-600 to-rose-700 rounded-2xl p-6 text-left shadow-lg shadow-pink-500/20 hover:shadow-xl hover:shadow-pink-500/30">
      <div class="flex items-center gap-3 mb-4">
       <div class="w-12 h-12 bg-white/20 rounded-xl flex items-center justify-center"><span class="text-2xl">🎨</span>
       </div><span class="bg-white/20 text-white text-xs font-medium px-3 py-1 rounded-full">Due: Week 8</span>
      </div><h3 class="text-xl font-bold text-white mb-2">Assignment 4</h3><p class="text-pink-100 text-sm">Creative Design</p></button> <!-- Assignment 5 --> <button onclick="openModal(4)" class="assignment-card bg-gradient-to-br from-fuchsia-500 to-pink-600 rounded-2xl p-6 text-left shadow-lg shadow-fuchsia-500/20 hover:shadow-xl hover:shadow-fuchsia-500/30">
      <div class="flex items-center gap-3 mb-4">
       <div class="w-12 h-12 bg-white/20 rounded-xl flex items-center justify-center"><span class="text-2xl">🎯</span>
       </div><span class="bg-white/20 text-white text-xs font-medium px-3 py-1 rounded-full">Due: Week 10</span>
      </div><h3 class="text-xl font-bold text-white mb-2">Assignment 5</h3><p class="text-pink-100 text-sm">Final Project</p></button>
    </div>
   </div><!-- Modal -->
   <div id="modal" class="fixed inset-0 z-50 hidden">
    <div class="modal-backdrop absolute inset-0 bg-black/60 backdrop-blur-sm" onclick="closeModal()"></div>
    <div class="flex items-center justify-center min-h-full p-4">
     <div class="modal-content relative bg-slate-800 rounded-3xl w-full max-w-lg shadow-2xl overflow-hidden"><!-- Modal Header -->
      <div id="modal-header" class="p-6 bg-gradient-to-r from-pink-500 to-rose-600">
       <div class="flex items-center justify-between">
        <div class="flex items-center gap-4">
         <div class="w-14 h-14 bg-white/20 rounded-2xl flex items-center justify-center"><span id="modal-icon" class="text-3xl">📝</span>
         </div>
         <div>
          <h2 id="modal-title" class="text-2xl font-bold text-white">Assignment 1</h2>
          <p id="modal-type" class="text-white/80">Research &amp; Analysis</p>
         </div>
        </div><button onclick="closeModal()" class="w-10 h-10 bg-white/20 hover:bg-white/30 rounded-xl flex items-center justify-center transition-colors">
         <svg class="w-5 h-5 text-white" fill="none" stroke="currentColor" viewbox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
         </svg></button>
       </div>
      </div><!-- Modal Body -->
      <div class="p-6">
       <div class="space-y-4">
        <div class="flex items-center gap-3 text-slate-300">
         <svg class="w-5 h-5 text-purple-400" fill="none" stroke="currentColor" viewbox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8 7V3m8 4V3m-9 8h10M5 21h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v12a2 2 0 002 2z" />
         </svg><span id="modal-due" class="font-medium">Due: Week 2</span>
        </div>
        <div class="bg-slate-700/50 rounded-2xl p-4">
         <h4 class="text-white font-semibold mb-2">Description</h4>
         <p id="modal-description" class="text-slate-300 text-sm leading-relaxed">Complete a comprehensive research paper analyzing current trends in your field of study. Include at least 5 academic sources and provide critical analysis.</p>
        </div>
        <div class="bg-slate-700/50 rounded-2xl p-4">
         <h4 class="text-white font-semibold mb-2">Requirements</h4>
         <ul id="modal-requirements" class="text-slate-300 text-sm space-y-2">
          <li class="flex items-start gap-2"><span class="text-purple-400 mt-0.5">•</span> <span>Minimum 2000 words</span></li>
          <li class="flex items-start gap-2"><span class="text-purple-400 mt-0.5">•</span> <span>APA citation format</span></li>
          <li class="flex items-start gap-2"><span class="text-purple-400 mt-0.5">•</span> <span>Include bibliography</span></li>
         </ul>
        </div>
       </div>
      </div>
     </div>
    </div>
   </div>
  </div>
  <script>
    const assignments = [
      {
        title: "Assignment 1",
        type: "Research & Analysis",
        icon: "📝",
        due: "Due: Week 2",
        gradient: "from-pink-500 to-rose-600",
        description: "Complete a comprehensive research paper analyzing current trends in your field of study. Include at least 5 academic sources and provide critical analysis.",
        requirements: ["Minimum 2000 words", "APA citation format", "Include bibliography"]
      },
      {
        title: "Assignment 2",
        type: "Programming Project",
        icon: "💻",
        due: "Due: Week 4",
        gradient: "from-violet-500 to-purple-600",
        description: "Build a functional web application that demonstrates your understanding of frontend and backend development concepts. Focus on clean code and documentation.",
        requirements: ["Fully functional application", "Code documentation", "User-friendly interface"]
      },
      {
        title: "Assignment 3",
        type: "Data Presentation",
        icon: "📊",
        due: "Due: Week 6",
        gradient: "from-cyan-500 to-blue-600",
        description: "Collect, analyze, and present data on a topic of your choice. Create visualizations that effectively communicate your findings to a non-technical audience.",
        requirements: ["Minimum 3 visualizations", "Written analysis report", "Data sources cited"]
      },
      {
        title: "Assignment 4",
        type: "Creative Design",
        icon: "🎨",
        due: "Due: Week 8",
        gradient: "from-amber-500 to-orange-600",
        description: "Design a complete brand identity for a fictional company, including logo, color palette, typography, and marketing materials that reflect the brand values.",
        requirements: ["Logo design", "Style guide document", "3 marketing mockups"]
      },
      {
        title: "Assignment 5",
        type: "Final Project",
        icon: "🎯",
        due: "Due: Week 10",
        gradient: "from-emerald-500 to-teal-600",
        description: "Combine all skills learned throughout the course to deliver a comprehensive final project. This should demonstrate mastery of research, development, and presentation.",
        requirements: ["Project proposal", "Working prototype", "Final presentation"]
      }
    ];

    const defaultConfig = {
      page_title: "Assignment Hub",
      subtitle: "Click on an assignment to view details",
      primary_color: "#1e1b4b",
      text_color: "#ffffff",
      accent_color: "#a855f7",
      font_family: "DM Sans"
    };

    function openModal(index) {
      const assignment = assignments[index];
      const modal = document.getElementById('modal');
      const header = document.getElementById('modal-header');
      
      document.getElementById('modal-icon').textContent = assignment.icon;
      document.getElementById('modal-title').textContent = assignment.title;
      document.getElementById('modal-type').textContent = assignment.type;
      document.getElementById('modal-due').textContent = assignment.due;
      document.getElementById('modal-description').textContent = assignment.description;
      
      header.className = `p-6 bg-gradient-to-r ${assignment.gradient}`;
      
      const reqList = document.getElementById('modal-requirements');
      reqList.innerHTML = assignment.requirements.map(req => `
        <li class="flex items-start gap-2">
          <span class="text-purple-400 mt-0.5">•</span>
          <span>${req}</span>
        </li>
      `).join('');
      
      modal.classList.remove('hidden');
      document.body.style.overflow = 'hidden';
    }

    function closeModal() {
      const modal = document.getElementById('modal');
      modal.classList.add('hidden');
      document.body.style.overflow = '';
    }

    document.addEventListener('keydown', (e) => {
      if (e.key === 'Escape') closeModal();
    });

    async function onConfigChange(config) {
      const title = config.page_title || defaultConfig.page_title;
      const subtitle = config.subtitle || defaultConfig.subtitle;
      const fontFamily = config.font_family || defaultConfig.font_family;
      
      document.getElementById('page-title').textContent = title;
      document.getElementById('subtitle').textContent = subtitle;
      document.body.style.fontFamily = `${fontFamily}, sans-serif`;
    }

    if (window.elementSdk) {
      window.elementSdk.init({
        defaultConfig,
        onConfigChange,
        mapToCapabilities: (config) => ({
          recolorables: [],
          borderables: [],
          fontEditable: {
            get: () => config.font_family || defaultConfig.font_family,
            set: (value) => window.elementSdk.setConfig({ font_family: value })
          },
          fontSizeable: undefined
        }),
        mapToEditPanelValues: (config) => new Map([
          ["page_title", config.page_title || defaultConfig.page_title],
          ["subtitle", config.subtitle || defaultConfig.subtitle]
        ])
      });
    }
  </script>
 <script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'9bfec1f236ae3c6f',t:'MTc2ODc0NjI4NC4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
