```react
import React, { useState, useEffect, useMemo } from 'react';
import {
  BookOpen,
  FileText,
  Calculator,
  BrainCircuit,
  CheckSquare,
  Clock,
  Search,
  Download,
  Eye,
  CheckCircle2,
  XCircle,
  Play,
  Pause,
  RotateCcw,
  Sun,
  Moon,
  Filter,
  Sparkles,
  Award,
  Layers,
  Check,
  Zap,
  Maximize2,
  ZoomIn,
  ZoomOut,
  ChevronRight,
  TrendingUp,
  ShieldCheck,
  HelpCircle,
  BarChart2
} from 'lucide-react';

// --- EXECUTIVE DATA & VARIANT 41 EXTENDED SPECIFICATIONS ---

const SUBJECTS = [
  { id: 'math-0580', code: '0580', name: 'Mathematics', category: 'Sciences & Math', tier: 'Core / Extended', weight: 'Multiple Papers', color: 'from-blue-500 to-indigo-600' },
  { id: 'physics-0625', code: '0625', name: 'Physics', category: 'Sciences & Math', tier: 'Core / Extended', weight: 'Multiple Papers', color: 'from-blue-600 to-blue-800' },
  { id: 'chem-0620', code: '0620', name: 'Chemistry', category: 'Sciences & Math', tier: 'Core / Extended', weight: 'Multiple Papers', color: 'from-sky-500 to-blue-600' },
  { id: 'cs-0478', code: '0478', name: 'Computer Science', category: 'STEM', tier: 'Standard', weight: 'Multiple Papers', color: 'from-indigo-500 to-blue-700' },
  { id: 'bio-0610', code: '0610', name: 'Biology', category: 'Sciences & Math', tier: 'Core / Extended', weight: 'Multiple Papers', color: 'from-cyan-500 to-blue-600' }
];

const PAST_PAPERS = [
  { id: 'pp-1', subjectId: 'physics-0625', year: 2026, series: 'May/June', paperNum: 'Paper 4', variant: 'Variant 41 (Theory)', type: 'QP', title: '0625_s26_qp_41.pdf', size: '2.8 MB', solvedRatio: '100% Verified' },
  { id: 'pp-2', subjectId: 'physics-0625', year: 2026, series: 'May/June', paperNum: 'Paper 4', variant: 'Variant 41 (Theory)', type: 'MS', title: '0625_s26_ms_41.pdf', size: '1.4 MB', solvedRatio: 'Official CAIE' },
  { id: 'pp-3', subjectId: 'physics-0625', year: 2026, series: 'May/June', paperNum: 'Paper 2', variant: 'Variant 22 (Multiple Choice)', type: 'QP', title: '0625_s26_qp_22.pdf', size: '1.8 MB', solvedRatio: '100% Verified' },
  { id: 'pp-4', subjectId: 'physics-0625', year: 2026, series: 'May/June', paperNum: 'Paper 6', variant: 'Variant 62 (Alternative to Practical)', type: 'QP', title: '0625_s26_qp_62.pdf', size: '2.1 MB', solvedRatio: '100% Verified' },
  { id: 'pp-5', subjectId: 'math-0580', year: 2025, series: 'Oct/Nov', paperNum: 'Paper 4', variant: 'Variant 42 (Extended)', type: 'QP', title: '0580_w25_qp_42.pdf', size: '3.2 MB', solvedRatio: '100% Verified' },
  { id: 'pp-6', subjectId: 'math-0580', year: 2025, series: 'Oct/Nov', paperNum: 'Paper 2', variant: 'Variant 21 (Extended)', type: 'QP', title: '0580_w25_qp_21.pdf', size: '2.0 MB', solvedRatio: '100% Verified' },
  { id: 'pp-7', subjectId: 'chem-0620', year: 2025, series: 'May/June', paperNum: 'Paper 6', variant: 'Variant 61 (Alternative to Practical)', type: 'QP', title: '0620_s25_qp_61.pdf', size: '2.5 MB', solvedRatio: '100% Verified' },
  { id: 'pp-8', subjectId: 'chem-0620', year: 2025, series: 'May/June', paperNum: 'Paper 4', variant: 'Variant 41 (Theory)', type: 'QP', title: '0620_s25_qp_41.pdf', size: '2.6 MB', solvedRatio: '100% Verified' },
];

const PAST_PAPERS = [
  { id: 'pp-1', subjectId: 'physics-0625', year: 2026, series: 'May/June', variant: 'Paper 41 Extended Theory', type: 'QP', title: '0625_s26_qp_41.pdf', size: '2.8 MB', solvedRatio: '100% Verified' },
  { id: 'pp-2', subjectId: 'physics-0625', year: 2026, series: 'May/June', variant: 'Paper 41 Extended Theory', type: 'MS', title: '0625_s26_ms_41.pdf', size: '1.4 MB', solvedRatio: 'Official CAIE' },
  { id: 'pp-3', subjectId: 'math-0580', year: 2025, series: 'Oct/Nov', variant: 'Paper 41 Extended Mathematics', type: 'QP', title: '0580_w25_qp_41.pdf', size: '3.2 MB', solvedRatio: '100% Verified' },
  { id: 'pp-4', subjectId: 'math-0580', year: 2025, series: 'Oct/Nov', variant: 'Paper 41 Extended Mathematics', type: 'MS', title: '0580_w25_ms_41.pdf', size: '1.2 MB', solvedRatio: 'Official CAIE' },
  { id: 'pp-5', subjectId: 'chem-0620', year: 2025, series: 'May/June', variant: 'Paper 41 Extended Theory', type: 'QP', title: '0620_s25_qp_41.pdf', size: '2.6 MB', solvedRatio: '100% Verified' },
  { id: 'pp-6', subjectId: 'chem-0620', year: 2025, series: 'May/June', variant: 'Paper 41 Extended Theory', type: 'MS', title: '0620_s25_ms_41.pdf', size: '1.1 MB', solvedRatio: 'Official CAIE' },
  { id: 'pp-7', subjectId: 'physics-0625', year: 2024, series: 'May/June', variant: 'Paper 41 Extended Theory', type: 'QP', title: '0625_s24_qp_41.pdf', size: '2.4 MB', solvedRatio: '100% Verified' },
  { id: 'pp-8', subjectId: 'physics-0625', year: 2024, series: 'May/June', variant: 'Paper 41 Extended Theory', type: 'MS', title: '0625_s24_ms_41.pdf', size: '1.1 MB', solvedRatio: 'Official CAIE' },
];

const REVISION_NOTES = [
  {
    id: 'n-1',
    subjectId: 'physics-0625',
    topic: 'Extended Mechanics & Kinematics',
    subtopic: 'Equations of Uniformly Accelerated Motion (SUVAT)',
    summary: 'Mastering Paper 41 Extended multi-step motion problems with acceleration, displacement, and terminal velocity.',
    keyTerms: [
      { term: 'SUVAT Variables', def: 's = displacement, u = initial velocity, v = final velocity, a = acceleration, t = time' },
      { term: 'Terminal Velocity', def: 'Constant max speed attained when weight equals drag/air resistance.' },
      { term: 'Gradient of v-t Graph', def: 'Represents acceleration (a = Δv / Δt). Area under curve equals displacement (s).' }
    ],
    content: `
      ### 1. The Four Kinematic Equations (Extended Tier Only)
      For motion in a straight line with constant acceleration:
      1. $$v = u + at$$
      2. $$s = ut + \\frac{1}{2}at^2$$
      3. $$v^2 = u^2 + 2as$$
      4. $$s = \\left(\\frac{u + v}{2}\\right)t$$

      ### 2. Paper 41 Examination Technique
      - Always state your coordinate system (take upward or downward as positive).
      - Ensure units are converted to SI ($m/s$, $m/s^2$) before substituting into formulas.
    `,
    flashcards: [
      { q: "What does the area under a Velocity-Time graph represent?", a: "Total displacement (distance traveled in a specific direction)." },
      { q: "Which SUVAT equation connects displacement, initial velocity, acceleration, and time without final velocity?", a: "s = ut + 0.5 a t²" },
      { q: "At terminal velocity, what is the net resultant force on an object?", a: "Zero (Force of gravity = Drag force)." }
    ]
  },
  {
    id: 'n-2',
    subjectId: 'math-0580',
    topic: 'Extended Algebra & Calculus',
    subtopic: 'Differentiation & Turning Points (Paper 41 Core)',
    summary: 'Derivative rules d/dx(ax^n), finding gradients of curves, and local maxima/minima on Paper 4.',
    keyTerms: [
      { term: 'Derivative dy/dx', def: 'The instantaneous rate of change or gradient function of y with respect to x.' },
      { term: 'Turning Point Condition', def: 'Occurs where the gradient function dy/dx = 0.' },
      { term: 'Nature of Turning Point', def: 'Evaluate d²y/dx²: >0 indicates a minimum, <0 indicates a maximum.' }
    ],
    content: `
      ### 1. Power Rule of Differentiation
      If $$y = a x^n$$, then the derivative is:
      $$\\frac{dy}{dx} = a \\cdot n x^{n-1}$$

      ### 2. Finding Stationary Points
      Step 1: Calculate $$\\frac{dy}{dx}$$.  
      Step 2: Set $$\\frac{dy}{dx} = 0$$ and solve for $$x$$.  
      Step 3: Substitute $$x$$ back into the original curve equation to obtain the $$y$$-coordinate.
    `,
    flashcards: [
      { q: "What is the derivative of y = 4x³ - 5x + 7?", a: "dy/dx = 12x² - 5" },
      { q: "What condition defines a turning (stationary) point on a curve?", a: "dy/dx = 0" }
    ]
  },
  {
    id: 'n-3',
    subjectId: 'chem-0620',
    topic: 'Advanced Physical Chemistry',
    subtopic: 'Ideal Gas Law & Stoichiometry (Paper 41)',
    summary: 'Extended mole calculations incorporating gas volumes at non-RTP and concentration dynamics.',
    keyTerms: [
      { term: 'Ideal Gas Law', def: 'pV = nRT (p in Pa, V in m³, T in Kelvin).' },
      { term: 'Concentration (mol/dm³)', def: 'n = C × V (where V is in dm³).' }
    ],
    content: `
      ### 1. Ideal Gas Equation & Units
      $$p V = n R T$$
      - $$p$$ = pressure in Pascals ($1 \\text{ kPa} = 1000 \\text{ Pa}$)
      - $$V$$ = volume in cubic metres ($1 \\text{ m}^3 = 1000 \\text{ dm}^3$)
      - $$T$$ = temperature in Kelvin ($T(K) = T(^\\circ C) + 273$)
    `,
    flashcards: [
      { q: "How do you convert Celsius to Kelvin?", a: "T(K) = T(°C) + 273" },
      { q: "How many Pa are in 1.5 kPa?", a: "1500 Pa" }
    ]
  }
];

const FORMULAS = [
  {
    id: 'f-1',
    subjectId: 'physics-0625',
    title: 'Kinematics: Velocity Squared (SUVAT)',
    symbolic: 'v² = u² + 2as',
    variables: [
      { key: 'u', label: 'Initial Velocity u (m/s)', unit: 'm/s' },
      { key: 'a', label: 'Acceleration a (m/s²)', unit: 'm/s²' },
      { key: 's', label: 'Displacement s (m)', unit: 'm' }
    ],
    calcType: 'suvat',
    description: 'Calculates final velocity v given initial velocity, uniform acceleration, and displacement.'
  },
  {
    id: 'f-2',
    subjectId: 'math-0580',
    title: 'Quadratic Roots (Paper 4 Extended)',
    symbolic: 'x = (-b ± √(b² - 4ac)) / 2a',
    variables: [
      { key: 'a', label: 'Coefficient a (x²)', unit: '' },
      { key: 'b', label: 'Coefficient b (x)', unit: '' },
      { key: 'c', label: 'Constant c', unit: '' }
    ],
    calcType: 'quadratic',
    description: 'Computes exact real roots and discriminant value for Extended Paper 4 equations.'
  },
  {
    id: 'f-3',
    subjectId: 'chem-0620',
    title: 'Ideal Gas Equation',
    symbolic: 'pV = nRT',
    variables: [
      { key: 'p', label: 'Pressure p (Pa)', unit: 'Pa' },
      { key: 'v', label: 'Volume V (m³)', unit: 'm³' },
      { key: 't', label: 'Temperature T (K)', unit: 'K' }
    ],
    calcType: 'gasLaw',
    description: 'Finds moles (n) using gas constant R = 8.314 J/(mol·K).'
  },
  {
    id: 'f-4',
    subjectId: 'physics-0625',
    title: 'Specific Heat Capacity',
    symbolic: 'Q = m c ΔT',
    variables: [
      { key: 'm', label: 'Mass m (kg)', unit: 'kg' },
      { key: 'c', label: 'Specific Heat c (J/kg°C)', unit: 'J/kg°C' },
      { key: 'dt', label: 'Temp Change ΔT (°C)', unit: '°C' }
    ],
    calcType: 'thermal',
    description: 'Calculates thermal energy transferred in J.'
  }
];

const PRACTICE_QUESTIONS = [
  {
    id: 'q-1',
    subjectId: 'physics-0625',
    topic: 'Extended Kinematics (Paper 41)',
    difficulty: 'Paper 4 Extended (8 Marks)',
    question: 'A rocket accelerates uniformly from rest at 4.5 m/s² upward for a distance of 360 m. (a) Calculate its velocity at 360 m. (b) Calculate the time taken to cover this distance.',
    options: ['(a) 56.9 m/s, (b) 12.6 s', '(a) 40.0 m/s, (b) 10.0 s', '(a) 60.0 m/s, (b) 14.2 s', '(a) 56.9 m/s, (b) 8.0 s'],
    correctIndex: 0,
    markBreakdown: [
      { mark: 'M1', text: 'Select correct formula: v² = u² + 2as with u = 0.' },
      { mark: 'A1', text: 'v² = 0 + 2(4.5)(360) = 3240 -> v = 56.92 m/s (or 56.9 m/s).' },
      { mark: 'M1', text: 'Apply v = u + at -> 56.92 = 0 + (4.5)t.' },
      { mark: 'A1', text: 't = 56.92 / 4.5 = 12.65 s (or 12.6 s to 3 s.f.).' }
    ],
    examinerTip: 'Always show intermediate steps to secure M marks even if an arithmetic mistake occurs at the end.'
  },
  {
    id: 'q-2',
    subjectId: 'math-0580',
    topic: 'Extended Calculus / Turning Points',
    difficulty: 'Paper 41 Extended (7 Marks)',
    question: 'A curve has equation y = 2x³ - 9x² + 12x + 5. Find the coordinates of the two turning points and determine which is a local maximum.',
    options: ['(1, 10) Max, (2, 9) Min', '(1, 9) Min, (2, 10) Max', '(0, 5) Max, (3, 14) Min', '(2, 8) Max, (4, 12) Min'],
    correctIndex: 0,
    markBreakdown: [
      { mark: 'M1', text: 'Differentiate: dy/dx = 6x² - 18x + 12.' },
      { mark: 'M1', text: 'Set derivative to 0: 6(x² - 3x + 2) = 0 -> (x - 1)(x - 2) = 0.' },
      { mark: 'A1', text: 'x = 1 and x = 2.' },
      { mark: 'A1', text: 'At x = 1: y = 2(1) - 9(1) + 12(1) + 5 = 10 -> Point (1, 10).' },
      { mark: 'A1', text: 'At x = 2: y = 2(8) - 9(4) + 12(2) + 5 = 9 -> Point (2, 9).' },
      { mark: 'B1', text: 'd²y/dx² = 12x - 18. At x=1: d²y/dx² = -6 (<0, Maximum).' }
    ],
    examinerTip: 'Ensure you calculate both x AND y coordinates; omitting the y coordinate loses 2 accuracy marks on Paper 41.'
  }
];

const REVISION_TOPICS_CHECKLIST = [
  { id: 't-1', subjectId: 'physics-0625', name: 'Paper 41: SUVAT Kinematics & Momentum Vectoring', status: 'completed' },
  { id: 't-2', subjectId: 'physics-0625', name: 'Paper 41: Thermal Physics & Specific Latent Heat', status: 'completed' },
  { id: 't-3', subjectId: 'physics-0625', name: 'Paper 41: Electromagnetic Induction & Transformers', status: 'in-progress' },
  { id: 't-4', subjectId: 'math-0580', name: 'Paper 41: Differentiation & Turning Points', status: 'completed' },
  { id: 't-5', subjectId: 'math-0580', name: 'Paper 41: Vector Geometry & 3D Trigonometry', status: 'in-progress' },
  { id: 't-6', subjectId: 'chem-0620', name: 'Paper 41: Advanced Stoichiometry & Gas Volumes', status: 'completed' },
  { id: 't-7', subjectId: 'chem-0620', name: 'Paper 41: Organic Chemistry & Polymerization', status: 'not-started' },
];

export default function App() {
  const [activeTab, setActiveTab] = useState('past-papers');
  const [selectedSubject, setSelectedSubject] = useState('all');
  const [searchQuery, setSearchQuery] = useState('');

  const [yearFilter, setYearFilter] = useState('all');
  const [seriesFilter, setSeriesFilter] = useState('all');
  const [paperNumFilter, setPaperNumFilter] = useState('all');
  const [variantFilter, setVariantFilter] = useState('all');
  const [docTypeFilter, setDocTypeFilter] = useState('all');
  const [pdfModalDoc, setPdfModalDoc] = useState(null);
  const [showMarkSchemeInModal, setShowMarkSchemeInModal] = useState(true);

  const [selectedNote, setSelectedNote] = useState(REVISION_NOTES[0]);
  const [flashcardIdx, setFlashcardIdx] = useState(0);
  const [isFlipped, setIsFlipped] = useState(false);

  const [calcInputs, setCalcInputs] = useState({
    suvat: { u: '0', a: '4.5', s: '360' },
    quad: { a: '1', b: '-5', c: '6' },
    gasLaw: { p: '101325', v: '0.024', t: '298' },
    thermal: { m: '2.5', c: '4200', dt: '15' }
  });

  const [revealedAnswers, setRevealedAnswers] = useState({});
  const [selectedAnswers, setSelectedAnswers] = useState({});
  const [checklist, setChecklist] = useState(REVISION_TOPICS_CHECKLIST);

  const [pomoTime, setPomoTime] = useState(25 * 60);
  const [isPomoRunning, setIsPomoRunning] = useState(false);
  const [pomoMode, setPomoMode] = useState('work');

  useEffect(() => {
    let timer = null;
    if (isPomoRunning && pomoTime > 0) {
      timer = setInterval(() => setPomoTime((prev) => prev - 1), 1000);
    } else if (pomoTime === 0) {
      if (pomoMode === 'work') {
        setPomoMode('break');
        setPomoTime(5 * 60);
      } else {
        setPomoMode('work');
        setPomoTime(25 * 60);
      }
      setIsPomoRunning(false);
    }
    return () => clearInterval(timer);
  }, [isPomoRunning, pomoTime, pomoMode]);

  const formatPomoTime = (seconds) => {
    const mins = Math.floor(seconds / 60);
    const secs = seconds % 60;
    return `${mins.toString().padStart(2, '0')}:${secs.toString().padStart(2, '0')}`;
  };

  const filteredPapers = useMemo(() => {
    return PAST_PAPERS.filter((paper) => {
      if (selectedSubject !== 'all' && paper.subjectId !== selectedSubject) return false;
      if (yearFilter !== 'all' && paper.year.toString() !== yearFilter) return false;
      if (seriesFilter !== 'all' && paper.series !== seriesFilter) return false;
      if (paperNumFilter !== 'all' && paper.paperNum !== paperNumFilter) return false;
      if (variantFilter !== 'all' && !paper.variant.includes(variantFilter)) return false;
      if (docTypeFilter !== 'all' && paper.type !== docTypeFilter) return false;
      if (searchQuery.trim() !== '') {
        const query = searchQuery.toLowerCase();
        return paper.title.toLowerCase().includes(query) || paper.variant.toLowerCase().includes(query);
      }
      return true;
    });
  }, [selectedSubject, yearFilter, seriesFilter, paperNumFilter, variantFilter, docTypeFilter, searchQuery]);

      if (searchQuery.trim() !== '') {
        const query = searchQuery.toLowerCase();
        return paper.title.toLowerCase().includes(query) || paper.variant.toLowerCase().includes(query);
      }
      return true;
    });
  }, [selectedSubject, yearFilter, seriesFilter, docTypeFilter, searchQuery]);

  const handleCalcInputChange = (calcKey, field, val) => {
    setCalcInputs((prev) => ({
      ...prev,
      [calcKey]: { ...prev[calcKey], [field]: val }
    }));
  };

  const toggleChecklistStatus = (id) => {
    setChecklist((prev) =>
      prev.map((item) => {
        if (item.id === id) {
          const nextStatus = item.status === 'completed' ? 'in-progress' : item.status === 'in-progress' ? 'not-started' : 'completed';
          return { ...item, status: nextStatus };
        }
        return item;
      })
    );
  };

  return (
    <div className="min-h-screen font-sans bg-slate-50 text-slate-900">
      
      {/* --- TOP BAR --- */}
      <header className="border-b sticky top-0 z-40 bg-white/90 backdrop-blur-xl border-slate-200">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div className="flex items-center justify-between h-16">
            
            <div className="flex items-center gap-3">
              <div className="bg-gradient-to-tr from-blue-600 to-sky-500 p-2 rounded-xl text-white shadow-lg shadow-blue-500/20">
                <Award className="w-6 h-6 text-white" />
              </div>
              <div>
                <div className="flex items-center gap-2">
                  <span className="font-black text-xl tracking-tight text-blue-700">
                    ROMANA
                  </span>
                  <span className="text-[10px] uppercase font-bold tracking-widest px-2 py-0.5 rounded bg-blue-100 text-blue-700 border border-blue-200">
                    ACADEMIA
                  </span>
                </div>
                <div className="text-[11px] text-slate-500 font-medium">
                  Complete Past Paper Bank: <span className="text-blue-600 font-semibold">Paper 2, 4 & 6 (All Variants)</span>
                </div>
              </div>
            </div>

            <div className="flex-1 max-w-md mx-6 hidden md:block">
              <div className="relative">
                <Search className="w-4 h-4 absolute left-3 top-1/2 -translate-y-1/2 text-slate-400" />
                <input
                  type="text"
                  placeholder="Search papers by subject, year, code..."
                  value={searchQuery}
                  onChange={(e) => setSearchQuery(e.target.value)}
                  className="w-full pl-9 pr-4 py-1.5 rounded-lg text-xs font-medium outline-none transition border bg-slate-100 border-slate-200 text-slate-800 focus:border-blue-500 focus:ring-1 focus:ring-blue-500"
                />
              </div>
            </div>

            <div className="flex items-center gap-3">
              <div className="px-3 py-1 bg-blue-50 border border-blue-200 rounded-lg text-xs font-bold text-blue-700">
                All Papers & Variants
              </div>
            </div>

          </div>

          <nav className="flex space-x-1 sm:space-x-2 overflow-x-auto py-2 scrollbar-none border-t border-slate-100">
            {[
              { id: 'past-papers', label: 'Past Papers Bank', icon: FileText },
              { id: 'revision-notes', label: 'Extended Notes & Recall', icon: BookOpen },
              { id: 'formulae', label: 'Formula Solvers', icon: Calculator },
              { id: 'practice', label: 'Paper Practice Exam', icon: BrainCircuit },
              { id: 'tracker', label: 'Syllabus Mastery', icon: CheckSquare },
              { id: 'pomodoro', label: 'Focus Timer', icon: Clock }
            ].map((tab) => {
              const Icon = tab.icon;
              const isActive = activeTab === tab.id;
              return (
                <button
                  key={tab.id}
                  onClick={() => setActiveTab(tab.id)}
                  className={`flex items-center gap-2 px-3 py-1.5 rounded-lg text-xs font-semibold whitespace-nowrap transition-all ${
                    isActive
                      ? 'bg-blue-600 text-white shadow-md shadow-blue-500/20'
                      : 'text-slate-600 hover:text-blue-900 hover:bg-slate-100'
                  }`}
                >
                  <Icon className="w-3.5 h-3.5" />
                  {tab.label}
                </button>
              );
            })}
          </nav>
        </div>
      </header>

      {/* --- HERO SPECIFICATION HEADER --- */}
      <section className="border-b bg-white border-slate-200 py-6">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          
          <div className="flex flex-col lg:flex-row lg:items-center justify-between gap-4 mb-6">
            <div>
              <div className="flex items-center gap-2 mb-1">
                <span className="text-[10px] font-bold px-2 py-0.5 rounded bg-blue-100 text-blue-700 border border-blue-200">
                  PAPER 2, 4 & 6 ARCHIVE
                </span>
                <span className="text-[10px] font-bold px-2 py-0.5 rounded bg-sky-100 text-sky-700 border border-sky-200">
                  ALL VARIANTS (1, 2, 3)
                </span>
              </div>
              <h1 className="text-xl sm:text-2xl font-black tracking-tight text-slate-900">
                Cambridge IGCSE Past Paper Vault
              </h1>
              <p className="text-xs mt-1 text-slate-600">
                Access official Question Papers and Mark Schemes across Paper 2 (Multiple Choice), Paper 4 (Theory), and Paper 6 (Alternative to Practical) for all variants.
              </p>
            </div>
          </div>

          <div>
            <div className="text-[10px] font-bold uppercase tracking-wider text-slate-500 mb-2">
              Select Syllabus Subject
            </div>
            <div className="flex flex-wrap gap-2">
              <button
                onClick={() => setSelectedSubject('all')}
                className={`px-3 py-1.5 rounded-lg text-xs font-semibold transition ${
                  selectedSubject === 'all'
                    ? 'bg-blue-600 text-white font-bold shadow'
                    : 'bg-slate-100 text-slate-700 hover:bg-slate-200'
                }`}
              >
                All Subjects
              </button>
              {SUBJECTS.map((sub) => {
                const isSelected = selectedSubject === sub.id;
                return (
                  <button
                    key={sub.id}
                    onClick={() => setSelectedSubject(sub.id)}
                    className={`px-3 py-1.5 rounded-lg text-xs font-medium transition flex items-center gap-2 border ${
                      isSelected
                        ? 'bg-blue-50 border-blue-400 text-blue-700 font-bold shadow-sm'
                        : 'bg-white border-slate-200 text-slate-700 hover:bg-slate-50'
                    }`}
                  >
                    <span className="font-bold text-blue-600">{sub.code}</span>
                    <span>{sub.name}</span>
                  </button>
                );
              })}
            </div>
          </div>

        </div>
      </section>

      {/* --- MAIN PORTAL WORKSPACE --- */}
      <main className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-8">
        
        {activeTab === 'past-papers' && (
          <div className="space-y-6">
            
            <div className="p-4 rounded-xl border flex flex-wrap gap-4 items-center justify-between bg-white border-slate-200 shadow-sm">
              <div className="flex items-center gap-2 text-xs font-bold text-slate-700">
                <Filter className="w-4 h-4 text-blue-600" />
                <span>Paper & Variant Filter Engine</span>
              </div>

              <div className="flex flex-wrap gap-3">
                <select
                  value={paperNumFilter}
                  onChange={(e) => setPaperNumFilter(e.target.value)}
                  className="px-3 py-1.5 rounded-lg text-xs font-medium border outline-none bg-slate-50 border-slate-200 text-slate-800"
                >
                  <option value="all">All Papers (Paper 2, 4, 6)</option>
                  <option value="Paper 2">Paper 2 (MCQ)</option>
                  <option value="Paper 4">Paper 4 (Theory)</option>
                  <option value="Paper 6">Paper 6 (Alternative to Practical)</option>
                </select>

                <select
                  value={variantFilter}
                  onChange={(e) => setVariantFilter(e.target.value)}
                  className="px-3 py-1.5 rounded-lg text-xs font-medium border outline-none bg-slate-50 border-slate-200 text-slate-800"
                >
                  <option value="all">All Variants (1, 2, 3)</option>
                  <option value="Variant 1">Variant X1 (e.g. 11, 21, 41)</option>
                  <option value="Variant 2">Variant X2 (e.g. 12, 22, 42)</option>
                  <option value="Variant 3">Variant X3 (e.g. 13, 23, 43)</option>
                </select>

                <select
                  value={yearFilter}
                  onChange={(e) => setYearFilter(e.target.value)}
                  className="px-3 py-1.5 rounded-lg text-xs font-medium border outline-none bg-slate-50 border-slate-200 text-slate-800"
                >
                  <option value="all">All Years (2018 - 2026)</option>
                  <option value="2026">2026</option>
                  <option value="2025">2025</option>
                  <option value="2024">2024</option>
                </select>

                <select
                  value={seriesFilter}
                  onChange={(e) => setSeriesFilter(e.target.value)}
                  className="px-3 py-1.5 rounded-lg text-xs font-medium border outline-none bg-slate-50 border-slate-200 text-slate-800"
                >
                  <option value="all">All Series</option>
                  <option value="May/June">May / June Series</option>
                  <option value="Oct/Nov">Oct / Nov Series</option>
                </select>

                <select
                  value={docTypeFilter}
                  onChange={(e) => setDocTypeFilter(e.target.value)}
                  className="px-3 py-1.5 rounded-lg text-xs font-medium border outline-none bg-slate-50 border-slate-200 text-slate-800"
                >
                  <option value="all">All Documents</option>
                  <option value="QP">Question Papers (QP)</option>
                  <option value="MS">Mark Schemes (MS)</option>
                </select>
              </div>
            </div>

            <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4">
              {filteredPapers.map((paper) => {
                const sub = SUBJECTS.find((s) => s.id === paper.subjectId);

                return (
                  <div
                    key={paper.id}
                    className="p-5 rounded-xl border transition-all hover:shadow-md flex flex-col justify-between bg-white border-slate-200"
                  >
                    <div>
                      <div className="flex items-center justify-between mb-3">
                        <span className="text-[10px] font-bold px-2 py-0.5 rounded bg-blue-100 text-blue-700 border border-blue-200">
                          {sub?.code} • {paper.paperNum}
                        </span>
                        <span
                          className={`text-[10px] font-bold px-2 py-0.5 rounded ${
                            paper.type === 'QP' ? 'bg-sky-100 text-sky-700 border border-sky-200' : 'bg-emerald-100 text-emerald-700 border border-emerald-200'
                          }`}
                        >
                          {paper.type === 'QP' ? 'Question Paper' : 'Mark Scheme'}
                        </span>
                      </div>

                      <h3 className="font-bold text-sm text-slate-900 mb-1">{paper.variant}</h3>
                      <p className="text-xs text-slate-500 mb-3">
                        {paper.series} {paper.year} • {paper.size} • <span className="text-emerald-600 font-semibold">{paper.solvedRatio}</span>
                      </p>
                    </div>

                    <div className="flex items-center gap-2 pt-3 border-t border-slate-100">
                      <button
                        onClick={() => {
                          setPdfModalDoc(paper);
                          setShowMarkSchemeInModal(true);
                        }}
                        className="flex-1 flex items-center justify-center gap-1.5 py-2 px-3 rounded-lg text-xs font-bold bg-blue-600 hover:bg-blue-700 text-white transition shadow-sm"
                      >
                        <Eye className="w-3.5 h-3.5" />
                        Dual Workspace Preview
                      </button>
                    </div>
                  </div>
                );
              })}
            </div>
          </div>
        )}

        {
                      <span>{sub?.code} Extended</span>
                    </div>
                    <h4 className="font-bold text-sm text-slate-900">{note.topic}</h4>
                    <p className="text-xs text-slate-500 mt-1">{note.subtopic}</p>
                  </div>
                );
              })}
            </div>

            {selectedNote && (
              <div className="lg:col-span-2 space-y-6">
                <div className="p-6 rounded-xl border bg-white border-slate-200 shadow-sm">
                  <div className="border-b border-slate-100 pb-4 mb-4">
                    <span className="text-[10px] font-bold px-2 py-0.5 rounded bg-blue-100 text-blue-700 border border-blue-200">
                      {selectedNote.topic}
                    </span>
                    <h2 className="text-xl font-black mt-2 text-slate-900">{selectedNote.subtopic}</h2>
                    <p className="text-xs text-slate-500 mt-1">{selectedNote.summary}</p>
                  </div>

                  <div className="mb-6">
                    <h4 className="text-[10px] font-bold uppercase text-blue-600 tracking-wider mb-2">Paper 41 Core Terminology</h4>
                    <div className="grid grid-cols-1 gap-2">
                      {selectedNote.keyTerms.map((term, i) => (
                        <div key={i} className="p-3 rounded-lg text-xs border bg-slate-50 border-slate-200">
                          <strong className="text-blue-700 font-semibold">{term.term}: </strong>
                          <span className="text-slate-700">{term.def}</span>
                        </div>
                      ))}
                    </div>
                  </div>

                  <div className="text-xs text-slate-700 space-y-3 leading-relaxed">
                    {selectedNote.content.split('###').map((sec, idx) => {
                      if (!sec.trim()) return null;
                      const lines = sec.split('\n');
                      const title = lines[0];
                      const body = lines.slice(1).join('\n');
                      return (
                        <div key={idx} className="space-y-1">
                          <h3 className="font-bold text-sm text-blue-800">{title}</h3>
                          <p className="whitespace-pre-line">{body}</p>
                        </div>
                      );
                    })}
                  </div>
                </div>

                {selectedNote.flashcards && (
                  <div className="p-6 rounded-xl border bg-white border-slate-200 shadow-sm">
                    <div className="flex items-center justify-between mb-4">
                      <div className="flex items-center gap-2">
                        <Sparkles className="w-4 h-4 text-blue-600" />
                        <h3 className="font-bold text-xs uppercase tracking-wider text-slate-700">Active Recall Card</h3>
                      </div>
                      <span className="text-xs text-slate-500">
                        {flashcardIdx + 1} / {selectedNote.flashcards.length}
                      </span>
                    </div>

                    <div
                      onClick={() => setIsFlipped(!isFlipped)}
                      className={`min-h-[130px] p-6 rounded-xl border border-blue-200 flex flex-col items-center justify-center text-center cursor-pointer transition ${
                        isFlipped ? 'bg-blue-50 text-blue-900' : 'bg-slate-50 text-slate-900'
                      }`}
                    >
                      <span className="text-[10px] font-bold text-slate-500 mb-2">
                        {isFlipped ? 'ANSWER (CLICK TO FLIP)' : 'QUESTION (CLICK TO REVEAL)'}
                      </span>
                      <p className="text-sm font-semibold">
                        {isFlipped ? selectedNote.flashcards[flashcardIdx].a : selectedNote.flashcards[flashcardIdx].q}
                      </p>
                    </div>
                  </div>
                )}
              </div>
            )}
          </div>
        )}

        {activeTab === 'formulae' && (
          <div className="grid grid-cols-1 md:grid-cols-2 gap-6">
            {FORMULAS.map((item) => {
              const sub = SUBJECTS.find((s) => s.id === item.subjectId);
              return (
                <div key={item.id} className="p-6 rounded-xl border bg-white border-slate-200 shadow-sm">
                  <div className="flex justify-between items-start mb-3">
                    <div>
                      <span className="text-[10px] font-bold text-blue-600">{sub?.code}</span>
                      <h3 className="font-bold text-base text-slate-900">{item.title}</h3>
                    </div>
                    <span className="px-3 py-1 rounded-md text-xs font-mono font-bold bg-blue-100 text-blue-700 border border-blue-200">
                      {item.symbolic}
                    </span>
                  </div>

                  <p className="text-xs text-slate-500 mb-4">{item.description}</p>

                  <div className="p-4 rounded-lg border bg-slate-50 border-slate-200">
                    <h4 className="text-[10px] font-bold text-slate-500 uppercase tracking-wider mb-3">Interactive Extended Solver</h4>

                    {item.calcType === 'suvat' && (
                      <div className="space-y-3">
                        <div className="grid grid-cols-3 gap-2 text-xs">
                          <div>
                            <label className="text-slate-500 block mb-1">u (m/s)</label>
                            <input
                              type="number"
                              value={calcInputs.suvat.u}
                              onChange={(e) => handleCalcInputChange('suvat', 'u', e.target.value)}
                              className="w-full px-2 py-1 rounded border text-xs outline-none bg-white border-slate-300"
                            />
                          </div>
                          <div>
                            <label className="text-slate-500 block mb-1">a (m/s²)</label>
                            <input
                              type="number"
                              value={calcInputs.suvat.a}
                              onChange={(e) => handleCalcInputChange('suvat', 'a', e.target.value)}
                              className="w-full px-2 py-1 rounded border text-xs outline-none bg-white border-slate-300"
                            />
                          </div>
                          <div>
                            <label className="text-slate-500 block mb-1">s (m)</label>
                            <input
                              type="number"
                              value={calcInputs.suvat.s}
                              onChange={(e) => handleCalcInputChange('suvat', 's', e.target.value)}
                              className="w-full px-2 py-1 rounded border text-xs outline-none bg-white border-slate-300"
                            />
                          </div>
                        </div>
                        <div className="p-2.5 rounded bg-blue-100 text-xs text-blue-800 font-mono font-bold">
                          {(() => {
                            const u = parseFloat(calcInputs.suvat.u);
                            const a = parseFloat(calcInputs.suvat.a);
                            const s = parseFloat(calcInputs.suvat.s);
                            const v2 = u * u + 2 * a * s;
                            return v2 >= 0 ? `Computed Velocity v: ${Math.sqrt(v2).toFixed(2)} m/s` : 'Invalid kinematics inputs';
                          })()}
                        </div>
                      </div>
                    )}

                    {item.calcType === 'quadratic' && (
                      <div className="space-y-3">
                        <div className="grid grid-cols-3 gap-2 text-xs">
                          <div>
                            <label className="text-slate-500 block mb-1">a</label>
                            <input
                              type="number"
                              value={calcInputs.quad.a}
                              onChange={(e) => handleCalcInputChange('quad', 'a', e.target.value)}
                              className="w-full px-2 py-1 rounded border text-xs outline-none bg-white border-slate-300"
                            />
                          </div>
                          <div>
                            <label className="text-slate-500 block mb-1">b</label>
                            <input
                              type="number"
                              value={calcInputs.quad.b}
                              onChange={(e) => handleCalcInputChange('quad', 'b', e.target.value)}
                              className="w-full px-2 py-1 rounded border text-xs outline-none bg-white border-slate-300"
                            />
                          </div>
                          <div>
                            <label className="text-slate-500 block mb-1">c</label>
                            <input
                              type="number"
                              value={calcInputs.quad.c}
                              onChange={(e) => handleCalcInputChange('quad', 'c', e.target.value)}
                              className="w-full px-2 py-1 rounded border text-xs outline-none bg-white border-slate-300"
                            />
                          </div>
                        </div>
                        <div className="p-2.5 rounded bg-blue-100 text-xs text-blue-800 font-mono font-bold">
                          {(() => {
                            const a = parseFloat(calcInputs.quad.a);
                            const b = parseFloat(calcInputs.quad.b);
                            const c = parseFloat(calcInputs.quad.c);
                            const disc = b * b - 4 * a * c;
                            if (disc < 0) return 'Discriminant < 0 (No Real Roots)';
                            const x1 = ((-b + Math.sqrt(disc)) / (2 * a)).toFixed(3);
                            const x2 = ((-b - Math.sqrt(disc)) / (2 * a)).toFixed(3);
                            return `Exact Roots: x₁ = ${x1}, x₂ = ${x2}`;
                          })()}
                        </div>
                      </div>
                    )}

                  </div>
                </div>
              );
            })}
          </div>
        )}

        {activeTab === 'practice' && (
          <div className="max-w-3xl mx-auto space-y-6">
            <div className="flex items-center justify-between">
              <h2 className="text-base font-bold text-slate-900">Paper 4 Variant 41 Practice Suite</h2>
              <span className="text-xs text-blue-600 font-semibold">Includes Official M1/A1 Breakdown</span>
            </div>

            {PRACTICE_QUESTIONS.map((q) => {
              const sub = SUBJECTS.find((s) => s.id === q.subjectId);
              const selectedOpt = selectedAnswers[q.id];
              const isRevealed = revealedAnswers[q.id];

              return (
                <div key={q.id} className="p-6 rounded-xl border bg-white border-slate-200 shadow-sm">
                  <div className="flex items-center justify-between mb-3">
                    <span className="text-[10px] font-bold px-2 py-0.5 rounded bg-blue-100 text-blue-700 border border-blue-200">
                      {sub?.code} Extended
                    </span>
                    <span className="text-[10px] font-bold px-2 py-0.5 rounded bg-sky-100 text-sky-700 border border-sky-200">
                      {q.difficulty}
                    </span>
                  </div>

                  <p className="font-semibold text-sm leading-relaxed mb-4 text-slate-900">{q.question}</p>

                  <div className="grid grid-cols-1 sm:grid-cols-2 gap-2 mb-4">
                    {q.options.map((opt, idx) => {
                      const isSelected = selectedOpt === idx;
                      const isCorrect = idx === q.correctIndex;
                      let btnStyle = 'bg-slate-50 border-slate-200 text-slate-700 hover:bg-slate-100';

                      if (isSelected) {
                        btnStyle = isCorrect ? 'bg-emerald-50 border-emerald-300 text-emerald-800 font-bold' : 'bg-rose-50 border-rose-300 text-rose-800 font-bold';
                      }

                      return (
                        <button
                          key={idx}
                          onClick={() => setSelectedAnswers({ ...selectedAnswers, [q.id]: idx })}
                          className={`p-3 rounded-lg border text-left text-xs transition flex items-center justify-between ${btnStyle}`}
                        >
                          <span>{opt}</span>
                          {isSelected && (isCorrect ? <CheckCircle2 className="w-4 h-4 text-emerald-600" /> : <XCircle className="w-4 h-4 text-rose-600" />)}
                        </button>
                      );
                    })}
                  </div>

                  <div className="flex items-center justify-between pt-3 border-t border-slate-100">
                    <button
                      onClick={() => setRevealedAnswers({ ...revealedAnswers, [q.id]: !isRevealed })}
                      className="text-xs text-blue-600 hover:text-blue-800 font-bold flex items-center gap-1"
                    >
                      {isRevealed ? 'Hide Examiner Scheme' : 'Reveal Paper 4 M1/A1 Mark Breakdown'}
                    </button>
                  </div>

                  {isRevealed && (
                    <div className="mt-4 p-4 rounded-lg bg-blue-50 border border-blue-200 space-y-3">
                      <div className="text-xs font-bold text-blue-800 uppercase tracking-wider">Official Examiner Mark Scheme</div>
                      <div className="space-y-1.5">
                        {q.markBreakdown.map((m, idx) => (
                          <div key={idx} className="flex gap-2 text-xs text-slate-700">
                            <span className="font-mono font-bold text-blue-700">[{m.mark}]</span>
                            <span>{m.text}</span>
                          </div>
                        ))}
                      </div>
                      <div className="p-2 rounded bg-blue-100 text-[11px] text-blue-900 border border-blue-200">
                        <strong>Examiner Tip:</strong> {q.examinerTip}
                      </div>
                    </div>
                  )}
                </div>
              );
            })}
          </div>
        )}

        {activeTab === 'tracker' && (
          <div className="max-w-4xl mx-auto space-y-6">
            <div className="p-6 rounded-xl border bg-white border-slate-200 shadow-sm">
              <h2 className="text-base font-bold mb-1 text-slate-900">Paper 41 Syllabus Topics Tracker</h2>
              <p className="text-xs text-slate-500 mb-6">Monitor your confidence level across key extended paper modules.</p>

              <div className="space-y-3">
                {checklist.map((item) => {
                  return (
                    <div
                      key={item.id}
                      className="p-3.5 rounded-lg border flex items-center justify-between transition bg-slate-50 border-slate-200"
                    >
                      <div className="flex items-center gap-3">
                        <button
                          onClick={() => toggleChecklistStatus(item.id)}
                          className={`w-5 h-5 rounded flex items-center justify-center border transition ${
                            item.status === 'completed'
                              ? 'bg-blue-600 border-blue-600 text-white font-bold'
                              : 'border-slate-300 bg-white'
                          }`}
                        >
                          {item.status === 'completed' && <Check className="w-3.5 h-3.5" />}
                        </button>
                        <span className="text-xs font-semibold text-slate-800">{item.name}</span>
                      </div>

                      <span
                        className={`text-[10px] px-2.5 py-1 rounded font-bold uppercase ${
                          item.status === 'completed' ? 'bg-blue-100 text-blue-700' : 'bg-slate-200 text-slate-600'
                        }`}
                      >
                        {item.status === 'completed' ? 'Mastered' : 'In Progress'}
                      </span>
                    </div>
                  );
                })}
              </div>
            </div>
          </div>
        )}

        {activeTab === 'pomodoro' && (
          <div className="max-w-md mx-auto">
            <div className="p-8 rounded-2xl border text-center space-y-6 bg-white border-slate-200 shadow-lg">
              <span className="text-[10px] font-bold px-3 py-1 rounded-full bg-blue-100 text-blue-700 border border-blue-200 uppercase tracking-wider">
                {pomoMode === 'work' ? 'Exam Focus Mode' : 'Rest Interval'}
              </span>

              <h2 className="text-5xl font-black font-mono tracking-tight text-slate-900">
                {formatPomoTime(pomoTime)}
              </h2>

              <div className="flex justify-center gap-4">
                <button
                  onClick={() => setIsPomoRunning(!isPomoRunning)}
                  className="p-4 rounded-full font-bold bg-blue-600 text-white hover:bg-blue-700 transition shadow-md"
                >
                  {isPomoRunning ? <Pause className="w-6 h-6" /> : <Play className="w-6 h-6 ml-0.5" />}
                </button>
                <button
                  onClick={() => {
                    setIsPomoRunning(false);
                    setPomoTime(pomoMode === 'work' ? 25 * 60 : 5 * 60);
                  }}
                  className="p-4 rounded-full border border-slate-300 bg-slate-100 text-slate-700 hover:bg-slate-200"
                >
                  <RotateCcw className="w-5 h-5" />
                </button>
              </div>
            </div>
          </div>
        )}

      </main>

      {pdfModalDoc && (
        <div className="fixed inset-0 z-50 flex items-center justify-center p-4 bg-black/50 backdrop-blur-sm">
          <div className="w-full max-w-5xl rounded-2xl border shadow-2xl overflow-hidden flex flex-col max-h-[90vh] bg-white border-slate-200">
            
            <div className="p-4 border-b border-slate-200 flex flex-wrap items-center justify-between gap-2 bg-slate-50">
              <div>
                <h3 className="font-bold text-sm text-slate-900">{pdfModalDoc.title}</h3>
                <p className="text-xs text-slate-500">{pdfModalDoc.variant} • {pdfModalDoc.series} {pdfModalDoc.year}</p>
              </div>

              <div className="flex items-center gap-2">
                <button
                  onClick={() => setShowMarkSchemeInModal(!showMarkSchemeInModal)}
                  className={`px-3 py-1.5 rounded-lg text-xs font-bold border transition ${
                    showMarkSchemeInModal ? 'bg-blue-600 border-blue-600 text-white' : 'bg-white border-slate-300 text-slate-700'
                  }`}
                >
                  {showMarkSchemeInModal ? 'Split MS View Active' : 'Enable Split Mark Scheme'}
                </button>

                <button
                  onClick={() => setPdfModalDoc(null)}
                  className="p-1.5 rounded-lg text-slate-500 hover:text-slate-900 hover:bg-slate-200"
                >
                  ✕
                </button>
              </div>
            </div>

            <div className="flex-1 overflow-y-auto p-6 bg-slate-100 grid grid-cols-1 md:grid-cols-2 gap-4">
              
              <div className="p-5 rounded-xl bg-white border border-slate-200 space-y-4 text-xs font-mono shadow-sm">
                <div className="border-b border-slate-200 pb-2 text-blue-700 font-bold flex justify-between">
                  <span>CAMBRIDGE EXTENDED PAPER 41</span>
                  <span>[QUESTION PAPER]</span>
                </div>
                <p className="text-slate-800">
                  <strong>Question 1:</strong> A ball is thrown vertically upward with an initial velocity of 18 m/s. Calculate the maximum height reached. [3 marks]
                </p>
                <div className="text-slate-400 italic py-6 border-b border-slate-100">
                  [Simulated Paper 41 Workspace Area - 8 Pages Total]
                </div>
              </div>

              {showMarkSchemeInModal && (
                <div className="p-5 rounded-xl bg-blue-50/50 border border-blue-200 space-y-4 text-xs font-mono shadow-sm">
                  <div className="border-b border-blue-200 pb-2 text-blue-800 font-bold flex justify-between">
                    <span>OFFICIAL MARK SCHEME</span>
                    <span>[MS 41]</span>
                  </div>
                  <div className="space-y-2 text-blue-900">
                    <p><strong>1(a) M1:</strong> v² = u² + 2as with v = 0.</p>
                    <p><strong>1(a) M1:</strong> 0 = 18² + 2(-9.81)s.</p>
                    <p><strong>1(a) A1:</strong> s = 324 / 19.62 = 16.5 m.</p>
                  </div>
                </div>
              )}

            </div>

            <div className="p-4 border-t border-slate-200 flex justify-between items-center bg-slate-50">
              <span className="text-xs text-slate-500">Variant 41 Split Workspace Mode</span>
              <button
                onClick={() => alert(`Downloading: ${pdfModalDoc.title}`)}
                className="px-4 py-1.5 rounded-lg text-xs font-bold bg-blue-600 text-white flex items-center gap-1.5 shadow-sm hover:bg-blue-700"
              >
                <Download className="w-3.5 h-3.5" />
                Download Official PDF
              </button>
            </div>

          </div>
        </div>
      )}

    </div>
  );
}
      </main>

      {pdfModalDoc && (
        <div className="fixed inset-0 z-50 flex items-center justify-center p-4 bg-black/50 backdrop-blur-sm">
          <div className="w-full max-w-5xl rounded-2xl border shadow-2xl overflow-hidden flex flex-col max-h-[90vh] bg-white border-slate-200">
            
            <div className="p-4 border-b border-slate-200 flex flex-wrap items-center justify-between gap-2 bg-slate-50">
              <div>
                <h3 className="font-bold text-sm text-slate-900">{pdfModalDoc.title}</h3>
                <p className="text-xs text-slate-500">{pdfModalDoc.paperNum} • {pdfModalDoc.variant} • {pdfModalDoc.series} {pdfModalDoc.year}</p>
              </div>

              <div className="flex items-center gap-2">
                <button
                  onClick={() => setShowMarkSchemeInModal(!showMarkSchemeInModal)}
                  className={`px-3 py-1.5 rounded-lg text-xs font-bold border transition ${
                    showMarkSchemeInModal ? 'bg-blue-600 border-blue-600 text-white' : 'bg-white border-slate-300 text-slate-700'
                  }`}
                >
                  {showMarkSchemeInModal ? 'Split MS View Active' : 'Enable Split Mark Scheme'}
                </button>

                <button
                  onClick={() => setPdfModalDoc(null)}
                  className="p-1.5 rounded-lg text-slate-500 hover:text-slate-900 hover:bg-slate-200"
                >
                  ✕
                </button>
              </div>
            </div>

            <div className="flex-1 overflow-y-auto p-6 bg-slate-100 grid grid-cols-1 md:grid-cols-2 gap-4">
              
              <div className="p-5 rounded-xl bg-white border border-slate-200 space-y-4 text-xs font-mono shadow-sm">
                <div className="border-b border-slate-200 pb-2 text-blue-700 font-bold flex justify-between">
                  <span>CAMBRIDGE PAST PAPER ARCHIVE</span>
                  <span>[{pdfModalDoc.paperNum.toUpperCase()} - {pdfModalDoc.variant}]</span>
                </div>
                <p className="text-slate-800">
                  <strong>Question 1:</strong> Sample examination question loaded for {pdfModalDoc.title}. Review instructions and answer spaces below.
                </p>
                <div className="text-slate-400 italic py-6 border-b border-slate-100">
                  [Simulated Official PDF Document Viewer - All Pages Active]
                </div>
              </div>

              {showMarkSchemeInModal && (
                <div className="p-5 rounded-xl bg-blue-50/50 border border-blue-200 space-y-4 text-xs font-mono shadow-sm">
                  <div className="border-b border-blue-200 pb-2 text-blue-800 font-bold flex justify-between">
                    <span>OFFICIAL MARK SCHEME</span>
                    <span>[{pdfModalDoc.paperNum}]</span>
                  </div>
                  <div className="space-y-2 text-blue-900">
                    <p><strong>1(a) Mark:</strong> Correct application of formula or data table reading.</p>
                    <p><strong>1(b) Mark:</strong> Correct unit and numerical precision (3 s.f.).</p>
                  </div>
                </div>
              )}

            </div>

            <div className="p-4 border-t border-slate-200 flex justify-between items-center bg-slate-50">
              <span className="text-xs text-slate-500">Dual Split Workspace Mode</span>
              <button
                onClick={() => alert(`Downloading: ${pdfModalDoc.title}`)}
                className="px-4 py-1.5 rounded-lg text-xs font-bold bg-blue-600 text-white flex items-center gap-1.5 shadow-sm hover:bg-blue-700"
              >
                <Download className="w-3.5 h-3.5" />
                Download Official PDF
              </button>
            </div>

          </div>
        </div>
      )}

    </div>
  );
}
```