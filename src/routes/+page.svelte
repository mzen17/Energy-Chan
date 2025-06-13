<script lang="ts">
    import { fly, fade, scale } from 'svelte/transition';
    import { cubicOut } from 'svelte/easing';
    import '../app.css';

    let show = true;

    // For navbar navigation
    const sections = [
        { id: "about", label: "About" },
        { id: "research", label: "Research Areas" },
        { id: "implementations", label: "Use Cases" },
        { id: "stream", label: "Stream" },
        { id: "faq", label: "FAQ" }
    ];
    function scrollToSection(id: string) {
        const el = document.getElementById(id);
        if (el) el.scrollIntoView({ behavior: "smooth", block: "start" });
    }
</script>

<!-- Background image -->
<div class="fixed inset-0 w-[100%] h-screen z-0 bg-cover bg-center pointer-events-none brightness-40" style="background-image: url('/BG.png');"></div>

<!-- Navbar -->
<nav class="top-0 left-0 w-[100%] z-10 bg-[rgba(30,10,10,0.92)] flex gap-5 px-10 py-3 items-center shadow-md backdrop-blur-md">
    {#each sections as section}
        <button
            class="text-[#ff6b6b] font-semibold text-[1.05rem] tracking-wide transition-colors duration-200 cursor-pointer px-3 py-1 rounded-md hover:bg-[rgba(255,107,107,0.12)] hover:text-white focus:outline-none"
            on:click={() => scrollToSection(section.id)}
            type="button"
        >
            {section.label}
        </button>
    {/each}
</nav>

<!-- Main container -->
<div class="max-w-4xl mx-auto mt-4 mb-10 p-8 bg-[rgba(30,10,10,0.80)] rounded-3xl shadow-2xl font-sans relative z-20 text-[#f2dede]" in:scale={{ duration: 600, easing: cubicOut }}>
    <h1 class="text-4xl font-bold mb-4 text-red-500" >Energy</h1>
    <p class="text-md text-white mb-4">
        Energy Engine is a framework for human recreation that attempts to allow computers to be virtually identical to a real-world human in a 3D contextual space. Rather than attempting to pass a singular Turing test involving a one time chat and a judge, Energy aims to solve indistinguisability in a 4D, world-wide context.
    </p>
    <div class="flex justify-center my-8 transition-transform" in:scale={{ duration: 600, delay: 400 }}>
        <img src="https://github.com/user-attachments/assets/a6dbcb91-bd31-4865-9c56-47c6ebf54535" alt="Energy-Chan 3D Model" class="rounded-xl shadow-xl max-w-full max-h-80 bg-[#2d1515] transition-transform duration-400 hover:scale-105 hover:-rotate-2" />
    </div>
    <div class="text-center text-sm text-[#ffb3b3] mb-8 -mt-4" in:fade={{ duration: 500, delay: 600 }}>
        [A 3D model of Energy-Chan being made in Blender by mzen17, subject to change to more detailed one]
    </div>

    <h2 id="about" class="text-2xl font-bold text-red-400 mt-10 mb-2">Research Areas</h2>
    <p class="text-[1.1rem] text-white mb-4">
        Energy aims to address 6 limited areas of modern day ML models by developing & integrating solutions.
    </p>

    <h3 id="performance" class="text-lg font-bold text-[#ff8787] mt-8 mb-2" in:fly={{ x: 40, duration: 600, delay: 1000 }}>Performance Testing</h3>
    <p class="text-[1.1rem] leading-relaxed mb-4" in:fade={{ duration: 600, delay: 1100 }}>
        We establish hard coded metrics to <b>ensure</b> our model is improving. These are tests/benchmarks custom designed, used on previous models and models from other vendors. Youtube is one of Energy-Chan's metrics, providing ATHR with access to feedback/reviews.
    </p>

    <h3 id="memory" class="text-lg font-bold text-[#ff8787] mt-8 mb-2" in:fly={{ x: 40, duration: 600, delay: 1200 }}>Memory</h3>
    <p class="text-[1.1rem] leading-relaxed mb-4" in:fade={{ duration: 600, delay: 1300 }}>
        Our model must be able to store and retrieve data in a human-like manner. To do this, we developed a complex system HLGraphRAG, inspired by Microsoft's GraphRAG, using weighted retrival graphs, allowing for high performance recall.
    </p>

    <h3 id="movement" class="text-lg font-bold text-[#ff8787] mt-8 mb-2" in:fly={{ x: 40, duration: 600, delay: 1400 }}>Movement</h3>
    <p class="text-[1.1rem] leading-relaxed mb-4" in:fade={{ duration: 600, delay: 1500 }}>
        Our model is capable of moving, conducting actions such as waving a hand when they want to or conducting executions on a computer.
    </p>

    <h3 id="realtime" class="text-lg font-bold text-[#ff8787] mt-8 mb-2" in:fly={{ x: 40, duration: 600, delay: 1600 }}>Real-time model & World</h3>
    <p class="text-[1.1rem] leading-relaxed mb-4" in:fade={{ duration: 600, delay: 1700 }}>
        Our model is capable of keeping track of a world, having real-time updates to its information to make the best and personalized choices with low response times.
    </p>

    <h3 id="agi" class="text-lg font-bold text-[#ff8787] mt-8 mb-2" in:fly={{ x: 40, duration: 600, delay: 1800 }}>AGI</h3>
    <p class="text-[1.1rem] leading-relaxed mb-4" in:fade={{ duration: 600, delay: 1900 }}>
        With every event/stream, our model gains new knowledge from the world and learns something new. Improving its score on tests is expected, intuition is not.
    </p>

    <h3 id="reinforcement" class="text-lg font-bold text-[#ff8787] mt-8 mb-2" in:fly={{ x: 40, duration: 600, delay: 2000 }}>Reinforcement</h3>
    <p class="text-[1.1rem] leading-relaxed mb-4" in:fade={{ duration: 600, delay: 2100 }}>
        The model has low rates of erroneous data. It's output matches the personality of the character, and it makes sense in a real world context.
    </p>

    <h2 id="schedule" class="text-2xl font-bold text-[#ff6b6b] mt-10 mb-2" in:fly={{ x: -40, duration: 600, delay: 2200 }}>Streaming Schedule</h2>
    <p class="text-[1.1rem] leading-relaxed mb-4" in:fade={{ duration: 600, delay: 2300 }}>
        The first stream (YT) is planned to be sometime in 2025. This may be pushed back depending on development of the model. I intend to stream every 2ish so weeks, subject to my availability. If there is a busy week or month, there may not be a stream.
    </p>

    <h3 id="content" class="text-lg font-bold text-[#ff8787] mt-8 mb-2" in:fly={{ x: 40, duration: 600, delay: 2400 }}>Content of Streams</h3>
    <p class="text-[1.1rem] leading-relaxed mb-2" in:fade={{ duration: 600, delay: 2500 }}>
        The stream is estimated to follow this breakdown:
    </p>
    <ul class="list-disc ml-6 mb-6 text-[1.1rem] leading-relaxed" in:fade={{ duration: 600, delay: 2600 }}>
        <li>30 minutes of implementation/work</li>
        <li>20 minutes of testing</li>
        <li>10 minutes of just driving the model around with life (random content like a clash of clans attack, a CS lecture, a MLBB match, etc)</li>
    </ul>
    <p class="text-[1.1rem] leading-relaxed mb-4" in:fade={{ duration: 600, delay: 2700 }}>
        As the model progresses, it is likely that the implementation time decreases and the model driving time increases.
    </p>

    <h2 id="faq" class="text-2xl font-bold text-[#ff6b6b] mt-10 mb-2" in:fly={{ x: -40, duration: 600, delay: 2800 }}>FAQ</h2>
    <div class="bg-[#2d1515] border-l-4 border-[#ff6b6b] p-6 rounded-lg my-8" in:fade={{ duration: 600, delay: 2900 }}>
        <h3 class="text-lg font-bold text-[#ff8787] mt-0 mb-2">Where to find the streams?</h3>
        <p class="text-[1.1rem] leading-relaxed mb-4">
            I will update this repo with a link sometime later.
        </p>
        <h3 class="text-lg font-bold text-[#ff8787] mt-6 mb-2">What is the different between this model and other current-day AI Youtube content such as Vedal & Neuro?</h3>
        <p class="text-[1.1rem] leading-relaxed mb-4">
            The difference is that Energy-Chan is primarily a research prototype that has entertainment as a <b>metric</b>. In addition, there are a few components of Energy-Chan not found in Neuro, such as 3D-spatial movement and the <b>memory engine (HLGraphRAG)</b> used for high performance recall.
        </p>
        <h3 class="text-lg font-bold text-[#ff8787] mt-6 mb-2">Code for AXNE?</h3>
        <p class="text-[1.1rem] leading-relaxed">
            Unfortunately, I have opted not to disclose the code for Auxilary Neural Engine. Energy-Chan is essentially proprietary, albeit this may change in the next few years or so.
        </p>
    </div>
</div>

<footer class="w-[100%] text-center text-[#ffb3b3] bg-[rgba(30,10,10,0.85)] py-5 text-base tracking-wide relative z-20 mt-10 rounded-t-2xl shadow-[0_-2px_16px_rgba(0,0,0,0.18)]">
    Copyright (C) 2025, Mike Zeng
</footer>
