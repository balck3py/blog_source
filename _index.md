---
title: "刘永超 - 全栈工程师"
---

<style>
/* ===== 全局样式重置 ===== */
.fullpage-cv {
  --cv-primary: #6366f1;
  --cv-primary-light: #818cf8;
  --cv-primary-dark: #4f46e5;
  --cv-accent: #06b6d4;
  --cv-accent-light: #22d3ee;
  --cv-gradient-1: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  --cv-gradient-2: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
  --cv-gradient-3: linear-gradient(135deg, #4facfe 0%, #00f2fe 100%);
  --cv-gradient-4: linear-gradient(135deg, #43e97b 0%, #38f9d7 100%);
  --cv-text: #1f2937;
  --cv-text-secondary: #6b7280;
  --cv-bg: #ffffff;
  --cv-bg-secondary: #f3f4f6;
  --cv-card-bg: rgba(255, 255, 255, 0.9);
  --cv-border: rgba(0, 0, 0, 0.1);
  --cv-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.15);
  --cv-glow: 0 0 40px rgba(99, 102, 241, 0.3);
}

.dark .fullpage-cv {
  --cv-text: #f9fafb;
  --cv-text-secondary: #9ca3af;
  --cv-bg: #0f172a;
  --cv-bg-secondary: #1e293b;
  --cv-card-bg: rgba(30, 41, 59, 0.9);
  --cv-border: rgba(255, 255, 255, 0.1);
  --cv-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.5);
  --cv-glow: 0 0 60px rgba(99, 102, 241, 0.4);
}

.fullpage-cv * {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.fullpage-cv {
  font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
  color: var(--cv-text);
  overflow: hidden;
  position: relative;
  width: 100vw;
  margin-left: calc(-50vw + 50%);
  background: var(--cv-bg);
}

/* ===== 全屏滚动容器 ===== */
.cv-container {
  height: 100vh;
  overflow-y: auto;
  scroll-snap-type: y mandatory;
  scroll-behavior: smooth;
}

.cv-section {
  min-height: 100vh;
  scroll-snap-align: start;
  scroll-snap-stop: always;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 2rem;
  position: relative;
  overflow: hidden;
  background: var(--cv-bg);
}

/* ===== 背景动画 ===== */
.cv-bg-animation {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  overflow: hidden;
  z-index: 0;
  pointer-events: none;
}

.cv-bg-animation::before {
  content: '';
  position: absolute;
  width: 200%;
  height: 200%;
  top: -50%;
  left: -50%;
  background: radial-gradient(circle at 20% 80%, var(--cv-primary) 0%, transparent 25%),
              radial-gradient(circle at 80% 20%, var(--cv-accent) 0%, transparent 25%),
              radial-gradient(circle at 40% 40%, var(--cv-primary-light) 0%, transparent 20%);
  opacity: 0.08;
  animation: cv-bg-rotate 30s linear infinite;
}

.dark .cv-bg-animation::before {
  opacity: 0.15;
}

@keyframes cv-bg-rotate {
  from { transform: rotate(0deg); }
  to { transform: rotate(360deg); }
}

/* 浮动粒子 */
.cv-particles {
  position: absolute;
  width: 100%;
  height: 100%;
  overflow: hidden;
}

.cv-particle {
  position: absolute;
  width: 4px;
  height: 4px;
  background: var(--cv-primary);
  border-radius: 50%;
  opacity: 0.4;
  animation: cv-float 15s infinite ease-in-out;
}

.cv-particle:nth-child(1) { left: 10%; animation-delay: 0s; animation-duration: 12s; }
.cv-particle:nth-child(2) { left: 20%; animation-delay: 2s; animation-duration: 14s; }
.cv-particle:nth-child(3) { left: 30%; animation-delay: 4s; animation-duration: 16s; }
.cv-particle:nth-child(4) { left: 40%; animation-delay: 1s; animation-duration: 13s; }
.cv-particle:nth-child(5) { left: 50%; animation-delay: 3s; animation-duration: 15s; }
.cv-particle:nth-child(6) { left: 60%; animation-delay: 5s; animation-duration: 11s; }
.cv-particle:nth-child(7) { left: 70%; animation-delay: 2s; animation-duration: 17s; }
.cv-particle:nth-child(8) { left: 80%; animation-delay: 4s; animation-duration: 14s; }
.cv-particle:nth-child(9) { left: 90%; animation-delay: 1s; animation-duration: 12s; }

@keyframes cv-float {
  0%, 100% { transform: translateY(100vh) scale(0); opacity: 0; }
  10% { opacity: 0.6; }
  90% { opacity: 0.6; }
  100% { transform: translateY(-100vh) scale(1); opacity: 0; }
}

/* ===== 内容区域 ===== */
.cv-content {
  position: relative;
  z-index: 1;
  width: 100%;
  max-width: 1200px;
  margin: 0 auto;
}

/* ===== Hero Section ===== */
.cv-hero {
  text-align: center;
}

.cv-hero-inner {
  animation: cv-fade-up 1s ease-out;
}

@keyframes cv-fade-up {
  from {
    opacity: 0;
    transform: translateY(40px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.cv-avatar-container {
  position: relative;
  display: inline-block;
  margin-bottom: 2rem;
}

.cv-avatar-img {
  width: 180px;
  height: 180px;
  border-radius: 50%;
  object-fit: cover;
  position: relative;
  z-index: 1;
  box-shadow: var(--cv-glow);
  animation: cv-pulse 3s ease-in-out infinite;
  border: 4px solid var(--cv-card-bg);
  cursor: pointer;
  transition: transform 0.3s ease;
}

.cv-avatar-img:hover {
  transform: scale(1.05);
}

/* 图片放大遮罩 */
.cv-lightbox {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.9);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 10000;
  opacity: 0;
  visibility: hidden;
  transition: all 0.3s ease;
  cursor: pointer;
}

.cv-lightbox.active {
  opacity: 1;
  visibility: visible;
}

.cv-lightbox-img {
  height: 70%;
  object-fit: contain;
  border-radius: 500px;
  box-shadow: 0 0 60px rgba(99, 102, 241, 0.5);
  transform: scale(0.8);
  transition: transform 0.3s ease;
}

.cv-lightbox.active .cv-lightbox-img {
  transform: scale(1);
}

.cv-lightbox-close-hint {
  position: absolute;
  bottom: 2rem;
  left: 50%;
  transform: translateX(-50%);
  color: rgba(255, 255, 255, 0.6);
  font-size: 0.9rem;
}

.cv-avatar {
  width: 160px;
  height: 160px;
  border-radius: 50%;
  background: var(--cv-gradient-1);
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 4rem;
  color: white;
  position: relative;
  z-index: 1;
  box-shadow: var(--cv-glow);
  animation: cv-pulse 3s ease-in-out infinite;
}

@keyframes cv-pulse {
  0%, 100% { box-shadow: var(--cv-glow); }
  50% { box-shadow: 0 0 80px rgba(99, 102, 241, 0.5); }
}

.cv-avatar-ring {
  position: absolute;
  top: -10px;
  left: -10px;
  right: -10px;
  bottom: -10px;
  border: 2px solid var(--cv-primary);
  border-radius: 50%;
  animation: cv-spin 10s linear infinite;
  border-top-color: transparent;
  border-right-color: transparent;
}

.cv-avatar-ring-2 {
  top: -20px;
  left: -20px;
  right: -20px;
  bottom: -20px;
  border-color: var(--cv-accent);
  border-top-color: transparent;
  border-left-color: transparent;
  animation: cv-spin-reverse 15s linear infinite;
}

@keyframes cv-spin {
  to { transform: rotate(360deg); }
}

@keyframes cv-spin-reverse {
  to { transform: rotate(-360deg); }
}

.cv-name {
  font-size: 3.5rem;
  font-weight: 800;
  margin-bottom: 0.5rem;
  background: var(--cv-gradient-1);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  padding: 0.5em 0;
}

.cv-title {
  font-size: 1.5rem;
  color: var(--cv-text-secondary);
  margin-bottom: 1.5rem;
  font-weight: 500;
}

.cv-title span {
  color: var(--cv-primary);
  font-weight: 600;
}

.cv-stats {
  display: flex;
  justify-content: center;
  gap: 3rem;
  margin: 2.5rem 0;
  flex-wrap: wrap;
}

.cv-stat {
  text-align: center;
}

.cv-stat-number {
  font-size: 3rem;
  font-weight: 800;
  background: var(--cv-gradient-3);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  line-height: 1;
}

.cv-stat-label {
  font-size: 0.875rem;
  color: var(--cv-text-secondary);
  margin-top: 0.5rem;
  text-transform: uppercase;
  letter-spacing: 0.1em;
}

.cv-contact-links {
  display: flex;
  justify-content: center;
  gap: 1rem;
  margin-top: 2rem;
  flex-wrap: wrap;
}

.cv-contact-link {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  padding: 0.75rem 1.5rem;
  background: var(--cv-card-bg);
  border: 1px solid var(--cv-border);
  border-radius: 50px;
  color: var(--cv-text);
  text-decoration: none;
  font-size: 0.9rem;
  transition: all 0.3s ease;
  backdrop-filter: blur(10px);
}

.cv-contact-link:hover {
  transform: translateY(-3px);
  box-shadow: var(--cv-shadow);
  border-color: var(--cv-primary);
  color: var(--cv-primary);
}

.cv-scroll-indicator {
  position: fixed;
  bottom: 2rem;
  left: 50%;
  transform: translateX(-50%);
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0.5rem;
  color: var(--cv-text-secondary);
  font-size: 0.8rem;
  animation: cv-bounce 2s infinite;
  z-index: 99;
  background: var(--cv-card-bg);
  padding: 0.75rem 1.5rem;
  border-radius: 50px;
  backdrop-filter: blur(10px);
  border: 1px solid var(--cv-border);
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
  transition: opacity 0.3s ease, visibility 0.3s ease;
}

.cv-scroll-indicator.hidden {
  opacity: 0;
  visibility: hidden;
}

@keyframes cv-bounce {
  0%, 100% { transform: translateX(-50%) translateY(0); }
  50% { transform: translateX(-50%) translateY(5px); }
}

.cv-scroll-indicator svg {
  width: 24px;
  height: 24px;
}

/* ===== Section Title ===== */
.cv-section-header {
  text-align: center;
  margin-bottom: 3rem;
}

.cv-section-title {
  display: inline-block;
  font-size: 2rem;
  font-weight: 700;
  color: white;
  margin-bottom: 0.75rem;
  padding: 0.75rem 2rem;
  background: var(--cv-gradient-1);
  border-radius: 50px;
  box-shadow: 0 4px 20px rgba(99, 102, 241, 0.3);
}

.cv-section-subtitle {
  color: var(--cv-text-secondary);
  font-size: 1.1rem;
}

/* ===== Skills Section ===== */
.cv-skills-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 2rem;
}

.cv-skill-card {
  background: var(--cv-card-bg);
  border: 1px solid var(--cv-border);
  border-radius: 20px;
  padding: 2rem;
  backdrop-filter: blur(10px);
  transition: all 0.4s ease;
  position: relative;
  overflow: hidden;
}

.cv-skill-card::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 4px;
  background: var(--cv-gradient-1);
  transform: scaleX(0);
  transform-origin: left;
  transition: transform 0.4s ease;
}

.cv-skill-card:hover::before {
  transform: scaleX(1);
}

.cv-skill-card:hover {
  transform: translateY(-8px);
  box-shadow: var(--cv-shadow);
}

.cv-skill-icon {
  width: 50px;
  height: 50px;
  border-radius: 12px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.5rem;
  margin-bottom: 1rem;
}

.cv-skill-icon.backend { background: linear-gradient(135deg, #667eea20, #764ba220); color: #667eea; }
.cv-skill-icon.frontend { background: linear-gradient(135deg, #f093fb20, #f5576c20); color: #f5576c; }
.cv-skill-icon.database { background: linear-gradient(135deg, #4facfe20, #00f2fe20); color: #4facfe; }
.cv-skill-icon.devops { background: linear-gradient(135deg, #43e97b20, #38f9d720); color: #43e97b; }
.cv-skill-icon.ai { background: linear-gradient(135deg, #fa709a20, #fee14020); color: #fa709a; }
.cv-skill-icon.other { background: linear-gradient(135deg, #a18cd120, #fbc2eb20); color: #a18cd1; }

.cv-skill-title {
  font-size: 1.25rem;
  font-weight: 600;
  margin-bottom: 1rem;
  color: var(--cv-text);
}

.cv-skill-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
}

.cv-skill-tag {
  padding: 0.35rem 0.75rem;
  background: var(--cv-bg-secondary);
  border-radius: 6px;
  font-size: 0.8rem;
  color: var(--cv-text-secondary);
  transition: all 0.3s ease;
}

.cv-skill-card:hover .cv-skill-tag {
  background: var(--cv-primary);
  color: white;
}

/* ===== Experience Section ===== */
.cv-timeline {
  position: relative;
  max-width: 900px;
  margin: 0 auto;
}

.cv-timeline::before {
  content: '';
  position: absolute;
  left: 20px;
  top: 0;
  bottom: 0;
  width: 2px;
  background: linear-gradient(to bottom, var(--cv-primary), var(--cv-accent));
}

@media (min-width: 768px) {
  .cv-timeline::before {
    left: 50%;
    transform: translateX(-50%);
  }
}

.cv-timeline-item {
  position: relative;
  padding-left: 60px;
  padding-bottom: 3rem;
}

@media (min-width: 768px) {
  .cv-timeline-item {
    width: 50%;
    padding-left: 0;
    padding-right: 40px;
  }

  .cv-timeline-item:nth-child(even) {
    margin-left: 50%;
    padding-left: 40px;
    padding-right: 0;
  }
}

.cv-timeline-dot {
  position: absolute;
  left: 12px;
  top: 0;
  width: 18px;
  height: 18px;
  background: var(--cv-primary);
  border-radius: 50%;
  border: 3px solid var(--cv-bg);
  box-shadow: 0 0 0 3px var(--cv-primary);
  z-index: 1;
}

@media (min-width: 768px) {
  .cv-timeline-dot {
    left: auto;
    right: -9px;
  }

  .cv-timeline-item:nth-child(even) .cv-timeline-dot {
    left: -9px;
    right: auto;
  }
}

.cv-timeline-content {
  background: var(--cv-card-bg);
  border: 1px solid var(--cv-border);
  border-radius: 16px;
  padding: 1.5rem;
  backdrop-filter: blur(10px);
  transition: all 0.3s ease;
}

.cv-timeline-content:hover {
  transform: translateY(-4px);
  box-shadow: var(--cv-shadow);
}

.cv-timeline-date {
  display: inline-block;
  padding: 0.35rem 0.75rem;
  background: var(--cv-gradient-1);
  color: white;
  border-radius: 6px;
  font-size: 0.8rem;
  font-weight: 500;
  margin-bottom: 0.75rem;
}

.cv-timeline-title {
  font-size: 1.25rem;
  font-weight: 600;
  color: var(--cv-text);
  margin-bottom: 0.25rem;
}

.cv-timeline-company {
  color: var(--cv-primary);
  font-weight: 500;
  margin-bottom: 0.75rem;
}

.cv-timeline-desc {
  color: var(--cv-text-secondary);
  font-size: 0.9rem;
  line-height: 1.6;
}

/* ===== Achievements Section ===== */
.cv-achievements {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 2rem;
}

.cv-achievement-card {
  background: var(--cv-card-bg);
  border: 1px solid var(--cv-border);
  border-radius: 20px;
  padding: 2rem;
  text-align: center;
  backdrop-filter: blur(10px);
  transition: all 0.4s ease;
  position: relative;
  overflow: hidden;
}

.cv-achievement-card::after {
  content: '';
  position: absolute;
  top: -50%;
  left: -50%;
  width: 200%;
  height: 200%;
  background: radial-gradient(circle, var(--cv-primary) 0%, transparent 70%);
  opacity: 0;
  transition: opacity 0.4s ease;
  pointer-events: none;
}

.cv-achievement-card:hover::after {
  opacity: 0.05;
}

.cv-achievement-card:hover {
  transform: translateY(-8px) scale(1.02);
  box-shadow: var(--cv-shadow);
}

.cv-achievement-number {
  font-size: 3.5rem;
  font-weight: 800;
  background: var(--cv-gradient-1);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  line-height: 1;
  margin-bottom: 0.5rem;
}

.cv-achievement-unit {
  font-size: 1.5rem;
}

.cv-achievement-label {
  font-size: 1rem;
  color: var(--cv-text);
  font-weight: 600;
  margin-bottom: 0.5rem;
}

.cv-achievement-desc {
  font-size: 0.85rem;
  color: var(--cv-text-secondary);
}

/* ===== Project Section ===== */
.cv-project-showcase {
  max-width: 900px;
  margin: 0 auto;
}

.cv-project-card {
  background: var(--cv-card-bg);
  border: 1px solid var(--cv-border);
  border-radius: 24px;
  padding: 2.5rem;
  backdrop-filter: blur(10px);
  position: relative;
  overflow: hidden;
}

.cv-project-card::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 6px;
  background: var(--cv-gradient-1);
}

.cv-project-header {
  display: flex;
  align-items: flex-start;
  justify-content: space-between;
  margin-bottom: 1.5rem;
  flex-wrap: wrap;
  gap: 1rem;
}

.cv-project-title {
  font-size: 1.75rem;
  font-weight: 700;
  color: var(--cv-text);
}

.cv-project-role {
  padding: 0.5rem 1rem;
  background: var(--cv-gradient-1);
  color: white;
  border-radius: 8px;
  font-size: 0.85rem;
  font-weight: 500;
}

.cv-project-desc {
  color: var(--cv-text-secondary);
  margin-bottom: 2rem;
  line-height: 1.7;
}

.cv-project-features {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 1rem;
  margin-bottom: 2rem;
}

.cv-project-feature {
  display: flex;
  align-items: flex-start;
  gap: 0.75rem;
  padding: 1rem;
  background: var(--cv-bg-secondary);
  border-radius: 12px;
}

.cv-project-feature-icon {
  width: 32px;
  height: 32px;
  border-radius: 8px;
  background: var(--cv-gradient-3);
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  flex-shrink: 0;
}

.cv-project-feature-text {
  font-size: 0.9rem;
  color: var(--cv-text);
}

.cv-project-tech {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
}

.cv-project-tech-tag {
  padding: 0.5rem 1rem;
  background: var(--cv-bg-secondary);
  border-radius: 8px;
  font-size: 0.8rem;
  color: var(--cv-text-secondary);
  border: 1px solid var(--cv-border);
}

/* ===== Education Section ===== */
.cv-education-card {
  background: var(--cv-card-bg);
  border: 1px solid var(--cv-border);
  border-radius: 24px;
  padding: 3rem;
  backdrop-filter: blur(10px);
  text-align: center;
  max-width: 600px;
  margin: 0 auto;
  position: relative;
  overflow: hidden;
}

.cv-education-icon {
  width: 80px;
  height: 80px;
  margin: 0 auto 1.5rem;
  background: var(--cv-gradient-1);
  border-radius: 20px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 2.5rem;
  color: white;
}

.cv-education-school {
  font-size: 2rem;
  font-weight: 700;
  color: var(--cv-text);
  margin-bottom: 0.5rem;
}

.cv-education-degree {
  font-size: 1.25rem;
  color: var(--cv-primary);
  margin-bottom: 0.25rem;
}

.cv-education-major {
  font-size: 1.1rem;
  color: var(--cv-text-secondary);
  margin-bottom: 1rem;
}

.cv-education-year {
  display: inline-block;
  padding: 0.5rem 1.5rem;
  background: var(--cv-bg-secondary);
  border-radius: 50px;
  font-size: 0.9rem;
  color: var(--cv-text-secondary);
}

/* ===== Contact Section ===== */
.cv-contact-section {
  text-align: center;
}

.cv-contact-cards {
  display: flex;
  justify-content: center;
  gap: 2rem;
  flex-wrap: wrap;
  margin-top: 2rem;
}

.cv-contact-card {
  background: var(--cv-card-bg);
  border: 1px solid var(--cv-border);
  border-radius: 20px;
  padding: 2rem 3rem;
  backdrop-filter: blur(10px);
  transition: all 0.3s ease;
  text-decoration: none;
  color: var(--cv-text);
}

.cv-contact-card:hover {
  transform: translateY(-8px);
  box-shadow: var(--cv-shadow);
  border-color: var(--cv-primary);
}

.cv-contact-card-icon {
  width: 60px;
  height: 60px;
  margin: 0 auto 1rem;
  background: var(--cv-gradient-1);
  border-radius: 16px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.5rem;
  color: white;
}

.cv-contact-card-title {
  font-size: 1rem;
  font-weight: 600;
  margin-bottom: 0.5rem;
}

.cv-contact-card-value {
  color: var(--cv-text-secondary);
  font-size: 0.9rem;
}

/* ===== Navigation Dots ===== */
.cv-nav-dots {
  position: fixed;
  right: 2rem;
  top: 50%;
  transform: translateY(-50%);
  display: flex;
  flex-direction: column;
  gap: 1rem;
  z-index: 100;
}

.cv-nav-dot {
  width: 12px;
  height: 12px;
  border-radius: 50%;
  background: var(--cv-border);
  cursor: pointer;
  transition: all 0.3s ease;
  border: none;
  padding: 0;
}

.cv-nav-dot:hover,
.cv-nav-dot.active {
  background: var(--cv-primary);
  transform: scale(1.3);
  box-shadow: 0 0 10px var(--cv-primary);
}

/* ===== Responsive ===== */
@media (max-width: 768px) {
  .cv-section {
    padding: 1rem;
  }

  .cv-name {
    font-size: 2.5rem;
  }

  .cv-title {
    font-size: 1.2rem;
  }

  .cv-stats {
    gap: 1.5rem;
  }

  .cv-stat-number {
    font-size: 2rem;
  }

  .cv-section-title {
    font-size: 1.5rem;
    padding: 0.6rem 1.5rem;
  }

  .cv-nav-dots {
    right: 1rem;
  }

  .cv-nav-dot {
    width: 10px;
    height: 10px;
  }

  .cv-achievement-number {
    font-size: 2.5rem;
  }

  .cv-project-card {
    padding: 1.5rem;
  }
}

/* ===== Animations for scroll reveal ===== */
.cv-reveal {
  opacity: 0;
  transform: translateY(30px);
  transition: all 0.8s ease;
}

.cv-reveal.visible {
  opacity: 1;
  transform: translateY(0);
}

.cv-reveal-delay-1 { transition-delay: 0.1s; }
.cv-reveal-delay-2 { transition-delay: 0.2s; }
.cv-reveal-delay-3 { transition-delay: 0.3s; }
.cv-reveal-delay-4 { transition-delay: 0.4s; }
.cv-reveal-delay-5 { transition-delay: 0.5s; }
.cv-reveal-delay-6 { transition-delay: 0.6s; }
</style>

<div class="fullpage-cv">
  <!-- 图片放大遮罩 -->
  <div class="cv-lightbox" id="cvLightbox">
    <img src="/eugen_hu_f06acf15e44d56d1.png" alt="刘永超" class="cv-lightbox-img">
    <span class="cv-lightbox-close-hint">点击任意位置关闭</span>
  </div>

  <!-- 向下滚动提示 -->
  <div class="cv-scroll-indicator" id="scrollIndicator">
    <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><polyline points="6 9 12 15 18 9"></polyline></svg>
  </div>

  <!-- Background Animation -->
  <div class="cv-bg-animation">
    <div class="cv-particles">
      <div class="cv-particle"></div>
      <div class="cv-particle"></div>
      <div class="cv-particle"></div>
      <div class="cv-particle"></div>
      <div class="cv-particle"></div>
      <div class="cv-particle"></div>
      <div class="cv-particle"></div>
      <div class="cv-particle"></div>
      <div class="cv-particle"></div>
    </div>
  </div>

  <!-- Navigation Dots -->
  <nav class="cv-nav-dots">
    <button class="cv-nav-dot active" data-section="0" title="首页"></button>
    <button class="cv-nav-dot" data-section="1" title="技能"></button>
    <button class="cv-nav-dot" data-section="2" title="经历"></button>
    <button class="cv-nav-dot" data-section="3" title="成就"></button>
    <button class="cv-nav-dot" data-section="4" title="项目"></button>
    <button class="cv-nav-dot" data-section="5" title="教育"></button>
    <button class="cv-nav-dot" data-section="6" title="联系"></button>
  </nav>

  <div class="cv-container" id="cvContainer">
    <!-- Section 1: Hero -->
    <section class="cv-section" id="section-0">
      <div class="cv-content cv-hero">
        <div class="cv-hero-inner">
          <div class="cv-avatar-container">
            <img src="/eugen_hu_f5698b6acde6dc20.png" alt="刘永超" class="cv-avatar-img">
            <div class="cv-avatar-ring"></div>
            <div class="cv-avatar-ring cv-avatar-ring-2"></div>
          </div>
          <h1 class="cv-name">刘永超</h1>
          <p class="cv-title"><span>全栈工程师</span> / 技术管理者 / AI探索者</p>
          <div class="cv-stats">
            <div class="cv-stat">
              <div class="cv-stat-number">12+</div>
              <div class="cv-stat-label">年开发经验</div>
            </div>
            <div class="cv-stat">
              <div class="cv-stat-number">6</div>
              <div class="cv-stat-label">年团队管理</div>
            </div>
            <div class="cv-stat">
              <div class="cv-stat-number">40+</div>
              <div class="cv-stat-label">团队规模</div>
            </div>
          </div>
          <div class="cv-contact-links">
            <a href="mailto:justnull@126.com" class="cv-contact-link">
              <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"></path><polyline points="22,6 12,13 2,6"></polyline></svg>
              justnull@126.com
            </a>
            <a href="tel:18516593569" class="cv-contact-link">
              <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6 19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 4.11 2h3a2 2 0 0 1 2 1.72 12.84 12.84 0 0 0 .7 2.81 2 2 0 0 1-.45 2.11L8.09 9.91a16 16 0 0 0 6 6l1.27-1.27a2 2 0 0 1 2.11-.45 12.84 12.84 0 0 0 2.81.7A2 2 0 0 1 22 16.92z"></path></svg>
              185-1659-3569
            </a>
            <span class="cv-contact-link">
              <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0 1 18 0z"></path><circle cx="12" cy="10" r="3"></circle></svg>
              上海
            </span>
          </div>
        </div>
      </div>
    </section>
    <!-- Section 2: Skills -->
    <section class="cv-section" id="section-1">
      <div class="cv-content">
        <div class="cv-section-header cv-reveal">
          <h2 class="cv-section-title">专业技能</h2>
          <p class="cv-section-subtitle">全栈技术栈 + AI应用能力</p>
        </div>
        <div class="cv-skills-grid">
          <div class="cv-skill-card cv-reveal cv-reveal-delay-1">
            <div class="cv-skill-icon backend">
              <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect x="2" y="3" width="20" height="14" rx="2" ry="2"></rect><line x1="8" y1="21" x2="16" y2="21"></line><line x1="12" y1="17" x2="12" y2="21"></line></svg>
            </div>
            <h3 class="cv-skill-title">后端开发</h3>
            <div class="cv-skill-tags">
              <span class="cv-skill-tag">.NET Core</span>
              <span class="cv-skill-tag">Python</span>
              <span class="cv-skill-tag">NodeJs-Koa</span>
              <span class="cv-skill-tag">EF Core</span>
              <span class="cv-skill-tag">Dapper</span>
            </div>
          </div>
          <div class="cv-skill-card cv-reveal cv-reveal-delay-2">
            <div class="cv-skill-icon frontend">
              <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><polygon points="12 2 2 7 12 12 22 7 12 2"></polygon><polyline points="2 17 12 22 22 17"></polyline><polyline points="2 12 12 17 22 12"></polyline></svg>
            </div>
            <h3 class="cv-skill-title">前端开发</h3>
            <div class="cv-skill-tags">
              <span class="cv-skill-tag">Angular 7-14</span>
              <span class="cv-skill-tag">Vue 2.x</span>
              <span class="cv-skill-tag">TypeScript</span>
              <span class="cv-skill-tag">Ant Design</span>
            </div>
          </div>
          <div class="cv-skill-card cv-reveal cv-reveal-delay-3">
            <div class="cv-skill-icon database">
              <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><ellipse cx="12" cy="5" rx="9" ry="3"></ellipse><path d="M21 12c0 1.66-4 3-9 3s-9-1.34-9-3"></path><path d="M3 5v14c0 1.66 4 3 9 3s9-1.34 9-3V5"></path></svg>
            </div>
            <h3 class="cv-skill-title">数据库</h3>
            <div class="cv-skill-tags">
              <span class="cv-skill-tag">PostgreSQL</span>
              <span class="cv-skill-tag">MySQL</span>
              <span class="cv-skill-tag">MSSQL</span>
              <span class="cv-skill-tag">Redis</span>
              <span class="cv-skill-tag">DuckDB</span>
            </div>
          </div>
          <div class="cv-skill-card cv-reveal cv-reveal-delay-4">
            <div class="cv-skill-icon devops">
              <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="3"></circle><path d="M19.4 15a1.65 1.65 0 0 0 .33 1.82l.06.06a2 2 0 0 1 0 2.83 2 2 0 0 1-2.83 0l-.06-.06a1.65 1.65 0 0 0-1.82-.33 1.65 1.65 0 0 0-1 1.51V21a2 2 0 0 1-2 2 2 2 0 0 1-2-2v-.09A1.65 1.65 0 0 0 9 19.4a1.65 1.65 0 0 0-1.82.33l-.06.06a2 2 0 0 1-2.83 0 2 2 0 0 1 0-2.83l.06-.06a1.65 1.65 0 0 0 .33-1.82 1.65 1.65 0 0 0-1.51-1H3a2 2 0 0 1-2-2 2 2 0 0 1 2-2h.09A1.65 1.65 0 0 0 4.6 9a1.65 1.65 0 0 0-.33-1.82l-.06-.06a2 2 0 0 1 0-2.83 2 2 0 0 1 2.83 0l.06.06a1.65 1.65 0 0 0 1.82.33H9a1.65 1.65 0 0 0 1-1.51V3a2 2 0 0 1 2-2 2 2 0 0 1 2 2v.09a1.65 1.65 0 0 0 1 1.51 1.65 1.65 0 0 0 1.82-.33l.06-.06a2 2 0 0 1 2.83 0 2 2 0 0 1 0 2.83l-.06.06a1.65 1.65 0 0 0-.33 1.82V9a1.65 1.65 0 0 0 1.51 1H21a2 2 0 0 1 2 2 2 2 0 0 1-2 2h-.09a1.65 1.65 0 0 0-1.51 1z"></path></svg>
            </div>
            <h3 class="cv-skill-title">运维部署</h3>
            <div class="cv-skill-tags">
              <span class="cv-skill-tag">Docker [Compose]</span>
              <span class="cv-skill-tag">Kubernetes</span>
              <span class="cv-skill-tag">Aliyun</span>
              <span class="cv-skill-tag">CI/CD</span>
              <span class="cv-skill-tag">Linux</span>
            </div>
          </div>
          <div class="cv-skill-card cv-reveal cv-reveal-delay-5">
            <div class="cv-skill-icon ai">
              <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M12 2a2 2 0 0 1 2 2c0 .74-.4 1.39-1 1.73V7h1a7 7 0 0 1 7 7h1a2 2 0 0 1 0 4h-1v1a2 2 0 0 1-2 2h-1v1a2 2 0 0 1-4 0v-1H9v1a2 2 0 0 1-4 0v-1H4a2 2 0 0 1-2-2v-1H1a2 2 0 0 1 0-4h1a7 7 0 0 1 7-7h1V5.73A2 2 0 0 1 12 2"></path><circle cx="7.5" cy="14.5" r="1.5"></circle><circle cx="16.5" cy="14.5" r="1.5"></circle></svg>
            </div>
            <h3 class="cv-skill-title">智能应用</h3>
            <div class="cv-skill-tags">
              <span class="cv-skill-tag">Ollama</span>
              <span class="cv-skill-tag">Transformers</span>
              <span class="cv-skill-tag">MCP</span>
              <span class="cv-skill-tag">RAG</span>
              <span class="cv-skill-tag">Qwen微调</span>
            </div>
          </div>
          <div class="cv-skill-card cv-reveal cv-reveal-delay-6">
            <div class="cv-skill-icon other">
              <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M21 16V8a2 2 0 0 0-1-1.73l-7-4a2 2 0 0 0-2 0l-7 4A2 2 0 0 0 3 8v8a2 2 0 0 0 1 1.73l7 4a2 2 0 0 0 2 0l7-4A2 2 0 0 0 21 16z"></path></svg>
            </div>
            <h3 class="cv-skill-title">其他技能</h3>
            <div class="cv-skill-tags">
              <span class="cv-skill-tag">Cloudflare</span>
              <span class="cv-skill-tag">Vercel</span>
              <span class="cv-skill-tag">微信小程序</span>
              <span class="cv-skill-tag">数据向量化</span>
            </div>
          </div>
        </div>
      </div>
    </section>
    <!-- Section 3: Experience -->
    <section class="cv-section" id="section-2">
      <div class="cv-content">
        <div class="cv-section-header cv-reveal">
          <h2 class="cv-section-title">工作经历</h2>
          <p class="cv-section-subtitle">从开发到管理的成长之路</p>
        </div>
        <div class="cv-timeline">
          <div class="cv-timeline-item cv-reveal cv-reveal-delay-1">
            <div class="cv-timeline-dot"></div>
            <div class="cv-timeline-content">
              <span class="cv-timeline-date">2025.09 - 至今</span>
              <h3 class="cv-timeline-title">.NET 开发工程师</h3>
              <p class="cv-timeline-company">上海元聚网络科技有限公司</p>
              <p class="cv-timeline-desc">负责业务需求开发、系统运维、服务拆解等工作。基于阿里云K8s进行系统运维管理，主导服务解耦和架构优化。</p>
            </div>
          </div>
          <div class="cv-timeline-item cv-reveal cv-reveal-delay-2">
            <div class="cv-timeline-dot"></div>
            <div class="cv-timeline-content">
              <span class="cv-timeline-date">2018.05 - 2025.01</span>
              <h3 class="cv-timeline-title">技术经理</h3>
              <p class="cv-timeline-company">上海森亿医疗科技有限公司</p>
              <p class="cv-timeline-desc">负责架构设计、技术管理、团队管理（40人）。主导微服务架构重构，实现亿级数据处理能力，系统可用性达99.99%。</p>
            </div>
          </div>
          <div class="cv-timeline-item cv-reveal cv-reveal-delay-3">
            <div class="cv-timeline-dot"></div>
            <div class="cv-timeline-content">
              <span class="cv-timeline-date">2017.05 - 2018.05</span>
              <h3 class="cv-timeline-title">全栈工程师</h3>
              <p class="cv-timeline-company">上海业霆网络科技有限公司</p>
              <p class="cv-timeline-desc">系统运维、需求对接、技术引进。性能优化300倍以上，推动系统从IIS迁移到Docker，从.NET Framework迁移到.NET Core。</p>
            </div>
          </div>
          <div class="cv-timeline-item cv-reveal cv-reveal-delay-4">
            <div class="cv-timeline-dot"></div>
            <div class="cv-timeline-content">
              <span class="cv-timeline-date">2015.05 - 2017.05</span>
              <h3 class="cv-timeline-title">.NET 开发工程师</h3>
              <p class="cv-timeline-company">新蛋信息技术（中国）有限公司</p>
              <p class="cv-timeline-desc">newegg.com主站开发，使用ZooKeeper+Thrift构建日志分发系统，优化推荐位商品脚本从分钟级提速到10秒内。</p>
            </div>
          </div>
        </div>
      </div>
    </section>
    <!-- Section 4: Achievements -->
    <section class="cv-section" id="section-3">
      <div class="cv-content">
        <div class="cv-section-header cv-reveal">
          <h2 class="cv-section-title">核心成就</h2>
          <p class="cv-section-subtitle">用数据说话的技术影响力</p>
        </div>
        <div class="cv-achievements">
          <div class="cv-achievement-card cv-reveal cv-reveal-delay-1">
            <div class="cv-achievement-number">400<span class="cv-achievement-unit">x</span></div>
            <div class="cv-achievement-label">任务效率提升</div>
            <div class="cv-achievement-desc">关键任务执行效率提升400倍</div>
          </div>
          <div class="cv-achievement-card cv-reveal cv-reveal-delay-2">
            <div class="cv-achievement-number">200<span class="cv-achievement-unit">x</span></div>
            <div class="cv-achievement-label">搜索性能提升</div>
            <div class="cv-achievement-desc">复杂搜索场景从小时缩减到秒</div>
          </div>
          <div class="cv-achievement-card cv-reveal cv-reveal-delay-3">
            <div class="cv-achievement-number">300<span class="cv-achievement-unit">%</span></div>
            <div class="cv-achievement-label">并发能力提升</div>
            <div class="cv-achievement-desc">架构升级后系统并发能力提升</div>
          </div>
          <div class="cv-achievement-card cv-reveal cv-reveal-delay-4">
            <div class="cv-achievement-number">99.99<span class="cv-achievement-unit">%</span></div>
            <div class="cv-achievement-label">系统可用性</div>
            <div class="cv-achievement-desc">微服务架构支撑千万级数据对接</div>
          </div>
          <div class="cv-achievement-card cv-reveal cv-reveal-delay-5">
            <div class="cv-achievement-number">2000<span class="cv-achievement-unit">万+</span></div>
            <div class="cv-achievement-label">年度营收</div>
            <div class="cv-achievement-desc">带领40人团队完成企业级平台建设</div>
          </div>
          <div class="cv-achievement-card cv-reveal cv-reveal-delay-6">
            <div class="cv-achievement-number">90<span class="cv-achievement-unit">%</span></div>
            <div class="cv-achievement-label">部署出错率降低</div>
            <div class="cv-achievement-desc">一键部署将交付周期从2周缩短到1小时</div>
          </div>
        </div>
      </div>
    </section>
    <!-- Section 5: Project -->
    <section class="cv-section" id="section-4">
      <div class="cv-content">
        <div class="cv-section-header cv-reveal">
          <h2 class="cv-section-title">核心项目</h2>
          <p class="cv-section-subtitle">临床科研一体化平台</p>
        </div>
        <div class="cv-project-showcase cv-reveal cv-reveal-delay-1">
          <div class="cv-project-card">
            <div class="cv-project-header">
              <h3 class="cv-project-title">临床科研一体化平台</h3>
              <span class="cv-project-role">架构设计 & 业务研发</span>
            </div>
            <p class="cv-project-desc">
              负责将医院各业务系统的数据进行同步、清洗、标准化处理，支持复杂条件的智能搜索、研究队列管理、专库研究、预测模型与统计分析等功能。服务100+客户，累计处理1000+需求。
            </p>
            <div class="cv-project-features">
              <div class="cv-project-feature">
                <div class="cv-project-feature-icon">
                  <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="22 12 18 12 15 21 9 3 6 12 2 12"></polyline></svg>
                </div>
                <span class="cv-project-feature-text">数据治理 - 亿级数据标准化与数据流设计</span>
              </div>
              <div class="cv-project-feature">
                <div class="cv-project-feature-icon">
                  <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="11" cy="11" r="8"></circle><line x1="21" y1="21" x2="16.65" y2="16.65"></line></svg>
                </div>
                <span class="cv-project-feature-text">智能搜索 - 支持复杂布尔逻辑条件检索</span>
              </div>
              <div class="cv-project-feature">
                <div class="cv-project-feature-icon">
                  <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M17 21v-2a4 4 0 0 0-4-4H5a4 4 0 0 0-4 4v2"></path><circle cx="9" cy="7" r="4"></circle><path d="M23 21v-2a4 4 0 0 0-3-3.87"></path><path d="M16 3.13a4 4 0 0 1 0 7.75"></path></svg>
                </div>
                <span class="cv-project-feature-text">研究队列 - 基于事件的研究课题管理</span>
              </div>
              <div class="cv-project-feature">
                <div class="cv-project-feature-icon">
                  <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><line x1="18" y1="20" x2="18" y2="10"></line><line x1="12" y1="20" x2="12" y2="4"></line><line x1="6" y1="20" x2="6" y2="14"></line></svg>
                </div>
                <span class="cv-project-feature-text">统计分析 - 预测模型与机器学习</span>
              </div>
            </div>
            <div class="cv-project-tech">
              <span class="cv-project-tech-tag">.NET Core</span>
              <span class="cv-project-tech-tag">Angular</span>
              <span class="cv-project-tech-tag">PostgreSQL</span>
              <span class="cv-project-tech-tag">Redis</span>
              <span class="cv-project-tech-tag">RabbitMQ</span>
              <span class="cv-project-tech-tag">SignalR</span>
              <span class="cv-project-tech-tag">Hangfire</span>
              <span class="cv-project-tech-tag">Docker</span>
            </div>
          </div>
        </div>
      </div>
    </section>
    <!-- Section 6: Education -->
    <section class="cv-section" id="section-5">
      <div class="cv-content">
        <div class="cv-section-header cv-reveal">
          <h2 class="cv-section-title">教育背景</h2>
          <p class="cv-section-subtitle">学历与专业</p>
        </div>
        <div class="cv-education-card cv-reveal cv-reveal-delay-1">
          <div class="cv-education-icon">
            <svg xmlns="http://www.w3.org/2000/svg" width="40" height="40" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M22 10v6M2 10l10-5 10 5-10 5z"/><path d="M6 12v5c3 3 9 3 12 0v-5"/></svg>
          </div>
          <h3 class="cv-education-school">东华大学</h3>
          <p class="cv-education-degree">本科</p>
          <p class="cv-education-major">计算机科学与技术</p>
          <span class="cv-education-year">2020 - 2023</span>
        </div>
      </div>
    </section>
    <!-- Section 7: Contact -->
    <section class="cv-section" id="section-6">
      <div class="cv-content cv-contact-section">
        <div class="cv-section-header cv-reveal">
          <h2 class="cv-section-title">联系我</h2>
          <p class="cv-section-subtitle">期待与您交流合作</p>
        </div>
        <div class="cv-contact-cards">
          <a href="mailto:justnull@126.com" class="cv-contact-card cv-reveal cv-reveal-delay-1">
            <div class="cv-contact-card-icon">
              <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"></path><polyline points="22,6 12,13 2,6"></polyline></svg>
            </div>
            <div class="cv-contact-card-title">邮箱</div>
            <div class="cv-contact-card-value">justnull@126.com</div>
          </a>
          <a href="tel:18516593569" class="cv-contact-card cv-reveal cv-reveal-delay-2">
            <div class="cv-contact-card-icon">
              <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6 19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 4.11 2h3a2 2 0 0 1 2 1.72 12.84 12.84 0 0 0 .7 2.81 2 2 0 0 1-.45 2.11L8.09 9.91a16 16 0 0 0 6 6l1.27-1.27a2 2 0 0 1 2.11-.45 12.84 12.84 0 0 0 2.81.7A2 2 0 0 1 22 16.92z"></path></svg>
            </div>
            <div class="cv-contact-card-title">电话</div>
            <div class="cv-contact-card-value">185-1659-3569</div>
          </a>
          <div class="cv-contact-card cv-reveal cv-reveal-delay-3">
            <div class="cv-contact-card-icon">
              <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0 1 18 0z"></path><circle cx="12" cy="10" r="3"></circle></svg>
            </div>
            <div class="cv-contact-card-title">位置</div>
            <div class="cv-contact-card-value">上海</div>
          </div>
        </div>
      </div>
    </section>
  </div>
</div>

<script>
(function() {
  // 获取DOM元素
  const container = document.getElementById('cvContainer');
  const sections = document.querySelectorAll('.cv-section');
  const navDots = document.querySelectorAll('.cv-nav-dot');
  const lightbox = document.getElementById('cvLightbox');
  const avatarImg = document.querySelector('.cv-avatar-img');
  const scrollIndicator = document.getElementById('scrollIndicator');

  // 头像点击放大
  if (avatarImg && lightbox) {
    avatarImg.addEventListener('click', () => {
      lightbox.classList.add('active');
    });

    lightbox.addEventListener('click', () => {
      lightbox.classList.remove('active');
    });

    // ESC键关闭
    document.addEventListener('keydown', (e) => {
      if (e.key === 'Escape' && lightbox.classList.contains('active')) {
        lightbox.classList.remove('active');
      }
    });
  }

  // 更新导航点状态
  function updateNavDots(index) {
    navDots.forEach((dot, i) => {
      dot.classList.toggle('active', i === index);
    });

    // 滚动到非首页时隐藏滚动指示器
    if (scrollIndicator) {
      if (index > 0) {
        scrollIndicator.classList.add('hidden');
      } else {
        scrollIndicator.classList.remove('hidden');
      }
    }
  }

  // 滚动到指定section
  function scrollToSection(index) {
    if (sections[index]) {
      sections[index].scrollIntoView({ behavior: 'smooth' });
    }
  }

  // 点击导航点
  navDots.forEach((dot, index) => {
    dot.addEventListener('click', () => {
      scrollToSection(index);
    });
  });

  // 点击滚动指示器滚动到下一页
  if (scrollIndicator) {
    scrollIndicator.addEventListener('click', () => {
      scrollToSection(1);
    });
    scrollIndicator.style.cursor = 'pointer';
  }

  // 监听滚动事件更新导航点
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        const index = Array.from(sections).indexOf(entry.target);
        updateNavDots(index);
      }
    });
  }, {
    root: container,
    threshold: 0.5
  });

  sections.forEach(section => observer.observe(section));

  // 滚动显示动画
  const revealObserver = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add('visible');
      }
    });
  }, {
    root: container,
    threshold: 0.1
  });

  document.querySelectorAll('.cv-reveal').forEach(el => {
    revealObserver.observe(el);
  });
})();
</script>
