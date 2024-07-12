import React, { useState } from 'react';
import { Home, User, Briefcase, Code, Book, Award, Mail, Cpu, Brain, FileCode, GraduationCap, MapPin, Phone, AtSign, Linkedin } from 'lucide-react';

const Navigation = ({ activeSection, setActiveSection }) => (
  <nav className="bg-gray-900 text-gray-300 p-4 sticky top-0 z-10 shadow-lg">
    <ul className="flex justify-around text-sm font-medium">
      {[
        { id: 'home', icon: Home, label: 'Home' },
        { id: 'about', icon: User, label: 'About' },
        { id: 'experience', icon: Briefcase, label: 'Experience' },
        { id: 'skills', icon: Code, label: 'Skills' },
        { id: 'projects', icon: Book, label: 'Projects' },
        { id: 'achievements', icon: Award, label: 'Achievements' },
        { id: 'contact', icon: Mail, label: 'Contact' },
      ].map(({ id, icon: Icon, label }) => (
        <li key={id}>
          <button
            onClick={() => setActiveSection(id)}
            className={`flex items-center transition-colors ${
              activeSection === id ? 'text-blue-400' : 'hover:text-blue-400'
            }`}
          >
            <Icon size={16} className="mr-2" /> {label}
          </button>
        </li>
      ))}
    </ul>
  </nav>
);

const Section = ({ id, title, icon: Icon, children }) => (
  <section className="p-8 rounded-lg shadow-md bg-gray-800 text-gray-300 min-h-[calc(100vh-80px)] overflow-y-auto">
    <h2 className="text-3xl font-bold mb-6 border-b border-gray-700 pb-2 flex items-center">
      <Icon size={24} className="mr-2 text-blue-400" />
      {title}
    </h2>
    {children}
  </section>
);

const Portfolio = () => {
  const [activeSection, setActiveSection] = useState('home');

  const sections = {
    home: (
      <Section id="home" title="Welcome" icon={Home}>
        <p className="text-2xl font-light leading-relaxed mb-4">I'm Pradip Prajapati, a Formal Verification Engineer with a passion for Neural Networks and hardware design.</p>
        <p className="text-lg leading-relaxed">Currently based in Bangalore, India, I'm open to exploring various roles in different stages of hardware design and verification.</p>
      </Section>
    ),
    about: (
      <Section id="about" title="About Me" icon={User}>
        <p className="text-lg leading-relaxed mb-4">I'm a Formal Verification Engineer at Intel, building efficient formal environments to assure quality on industry-leading hardware designs.</p>
        <p className="text-lg leading-relaxed mb-4">I graduated from the Indian Institute of Technology Gandhinagar with a Bachelor of Technology in Electrical Engineering, maintaining a CGPA of 8.81/10.</p>
        <p className="text-lg leading-relaxed">My interests lie in the intersection of hardware design, verification, and the application of Neural Networks to improve the chip design cycle.</p>
      </Section>
    ),
    experience: (
      <Section id="experience" title="Work Experience" icon={Briefcase}>
        <div className="mb-6">
          <h3 className="text-xl font-semibold mb-2 flex items-center"><Cpu size={20} className="mr-2 text-blue-400" />Formal Verification Engineer - Intel, Bangalore</h3>
          <p className="text-sm mb-2">June 2022 - Present</p>
          <ul className="list-disc pl-6 space-y-2 text-lg">
            <li>Formally verifying cutting-edge IP blocks for future products</li>
            <li>Building formal environments and implementing complexity reduction techniques</li>
            <li>Leading efforts to incorporate deep learning methodologies in formal methods</li>
            <li>Winner of the year-end live project bug hunting challenge</li>
          </ul>
        </div>
        <div className="mb-6">
          <h3 className="text-xl font-semibold mb-2 flex items-center"><FileCode size={20} className="mr-2 text-blue-400" />Design & Verification Intern - Redpine Signals</h3>
          <p className="text-sm mb-2">May 2021 - July 2021</p>
          <ul className="list-disc pl-6 space-y-2 text-lg">
            <li>Designed a concept for a hardware accelerator for Graphical Neural Networks</li>
            <li>Attained design and verification skills with Synopsys tools</li>
          </ul>
        </div>
        <div>
          <h3 className="text-xl font-semibold mb-2 flex items-center"><Brain size={20} className="mr-2 text-blue-400" />Machine Learning Intern - Necessario Innovations Pvt Ltd</h3>
          <p className="text-sm mb-2">May 2020 - July 2020</p>
          <ul className="list-disc pl-6 space-y-2 text-lg">
            <li>Developed face recognition and pedestrian removal features</li>
            <li>Worked with tools such as FastAI, OpenCV, and NumPy</li>
          </ul>
        </div>
      </Section>
    ),
    skills: (
      <Section id="skills" title="Skills" icon={Code}>
        <div className="mb-6">
          <h3 className="text-xl font-semibold mb-2 flex items-center"><Cpu size={20} className="mr-2 text-blue-400" />Technical Skills</h3>
          <ul className="list-disc pl-6 space-y-2 text-lg">
            <li>JasperGold, System Verilog, Python and Tcl scripting</li>
            <li>Abstraction techniques, State Space Tunnelling</li>
            <li>Python (Pandas, PyTorch, NumPy, Scikit-learn, etc.), C/C++, MATLAB</li>
            <li>Linux, Shell (Bash/Zsh), Git</li>
          </ul>
        </div>
        <div>
          <h3 className="text-xl font-semibold mb-2 flex items-center"><GraduationCap size={20} className="mr-2 text-blue-400" />Languages</h3>
          <ul className="list-disc pl-6 space-y-2 text-lg">
            <li>English: Professional proficiency</li>
            <li>French: Beginner proficiency</li>
            <li>Hindi: Native proficiency</li>
            <li>Gujarati: Bilingual proficiency</li>
          </ul>
        </div>
      </Section>
    ),
    projects: (
      <Section id="projects" title="Projects" icon={Book}>
        <ul className="space-y-6">
          <li>
            <h3 className="text-xl font-semibold mb-2 flex items-center"><Cpu size={20} className="mr-2 text-blue-400" />In-Memory Computing in 8T-SRAM Cell</h3>
            <p className="text-sm mb-2">Sep 2020 - Dec 2020 | Prof. Joycee Mekie, IIT Gandhinagar</p>
            <p className="text-lg">Explored power and area efficient method for faster dot product in DNNs using in-memory computation in 8T-SRAM cells.</p>
          </li>
          <li>
            <h3 className="text-xl font-semibold mb-2 flex items-center"><Brain size={20} className="mr-2 text-blue-400" />Image Restoration with Neural Diffusion Models</h3>
            <p className="text-sm mb-2">Jan 2022 - May 2022 | Prof. Shanmuganathan Raman, IIT Gandhinagar</p>
            <p className="text-lg">Created a deep neural network architecture for inpainting and other image restoration tasks using PyTorch.</p>
          </li>
          <li>
            <h3 className="text-xl font-semibold mb-2 flex items-center"><Brain size={20} className="mr-2 text-blue-400" />Air Quality Inference with Graph Neural Networks</h3>
            <p className="text-sm mb-2">Feb 2022 - May 2022 | Prof. Nipun Batra, IIT Gandhinagar</p>
            <p className="text-lg">Analyzed spatial and temporal correlation in air quality trends using Graph Neural Networks.</p>
          </li>
          <li>
            <h3 className="text-xl font-semibold mb-2 flex items-center"><FileCode size={20} className="mr-2 text-blue-400" />Sparse Online Modelling of Secondary Path for ANC</h3>
            <p className="text-sm mb-2">Feb 2022 - May 2022 | Prof. Nithin George, IIT Gandhinagar</p>
            <p className="text-lg">Implemented Re-weighted zero attracting algorithm for sparse modelling of secondary path in Active Noise Control.</p>
          </li>
        </ul>
      </Section>
    ),
    achievements: (
      <Section id="achievements" title="Achievements" icon={Award}>
        <ul className="space-y-4 text-lg">
          <li className="flex items-center">
            <Award size={20} className="mr-2 text-blue-400" />
            <span><span className="font-semibold">2022:</span> Winner, Year-end bug hunting challenge in real projects at FVCTO Intel India</span>
          </li>
          <li className="flex items-center">
            <Award size={20} className="mr-2 text-blue-400" />
            <span><span className="font-semibold">2020:</span> Cargill Global Scholar, Among top 10 in India and top 60 in the world</span>
          </li>
          <li className="flex items-center">
            <Award size={20} className="mr-2 text-blue-400" />
            <span><span className="font-semibold">2018:</span> Dean's list, Academic Excellence award during 4 out of 5 eligible semesters at IIT Gandhinagar</span>
          </li>
        </ul>
      </Section>
    ),
    contact: (
      <Section id="contact" title="Contact" icon={Mail}>
        <ul className="space-y-4 text-lg">
          <li className="flex items-center"><Phone size={20} className="mr-2 text-blue-400" /> +91-9727274937</li>
          <li className="flex items-center"><AtSign size={20} className="mr-2 text-blue-400" /> pradip.prajapati.official@gmail.com</li>
          <li className="flex items-center"><Linkedin size={20} className="mr-2 text-blue-400" /> <a href="https://linkedin.com/in/pradip-prajapati/" target="_blank" rel="noopener noreferrer" className="underline">linkedin.com/in/pradip-prajapati/</a></li>
          <li className="flex items-center"><MapPin size={20} className="mr-2 text-blue-400" /> Bangalore, India</li>
        </ul>
      </Section>
    ),
  };

  return (
    <div className="bg-gray-900 min-h-screen text-gray-300 font-sans">
      <Navigation activeSection={activeSection} setActiveSection={setActiveSection} />
      <div className="container mx-auto px-4 py-12">
        {sections[activeSection]}
      </div>
    </div>
  );
};

export default Portfolio;
