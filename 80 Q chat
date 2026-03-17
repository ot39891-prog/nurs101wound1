import React, { useMemo, useState } from "react";

const questions = [
  {
    id: 1,
    section: "Pharmacology / Med Admin",
    type: "Priority",
    question: "The nurse is preparing morning medications for four patients. Which situation should the nurse address first?",
    options: [
      "A patient asks whether a scheduled NSAID can be taken with food because it causes stomach upset",
      "A patient who is NPO has an order for an oral medication and all medications are currently being given through a feeding tube",
      "A patient receiving a nephrotoxic medication has a creatinine of 1.0 mg/dL",
      "A patient says the last dose of acetaminophen did not fully relieve pain"
    ],
    correct: [1],
    rationale: {
      whyCorrect: "All four options matter, but the feeding-tube patient presents an immediate medication-safety issue involving route mismatch. The nurse cannot independently reinterpret a PO order as a tube-administered order. This question combines medication rights, legal aspects of orders, and priority thinking. The key clue is that the ordered route and the available route do not match.",
      whyWrong: [
        "Giving NSAIDs with food is an appropriate teaching point, but this is not the most urgent safety issue.",
        "This creatinine is not abnormal, so there is no immediate sign that the medication must be withheld.",
        "Inadequate pain relief should be addressed, but it is not a higher priority than clarifying an unsafe order."
      ],
      tip: "When several answers look right, pick the one with the clearest immediate safety or legal barrier."
    }
  },
  {
    id: 2,
    section: "Pharmacology / Med Admin",
    type: "Clinical Scenario",
    question: "A nurse is interrupted while pouring medications and then returns to finish the pass. Which action best protects the patient?",
    options: [
      "Resume where the nurse left off because the medications were already selected",
      "Ask another nurse to administer the medications because the process was interrupted",
      "Restart the preparation process and complete the required medication checks before administration",
      "Administer only the time-sensitive medications and recheck the others later"
    ],
    correct: [2],
    rationale: {
      whyCorrect: "Several actions sound reasonable, but the best answer is to restart the process and repeat the required checks. Interruptions increase error risk, and the safest response is to rebuild accuracy from the beginning rather than relying on memory. This combines interruption safety with the 3-check process.",
      whyWrong: [
        "This sounds efficient, but it relies on memory after an interruption and increases error risk.",
        "Another nurse can help if needed, but that does not remove the need for a safe recheck process.",
        "Time pressure does not justify partial unsafe administration. Safety comes before speed."
      ],
      tip: "On hard med questions, efficiency is usually the distractor and safety is usually the winner."
    }
  },
  {
    id: 3,
    section: "Pharmacology / Med Admin",
    type: "SATA",
    question: "A nurse is reviewing whether a medication order is complete and safe to implement. Which findings require clarification before administration? Select all that apply.",
    options: [
      "The order lists the medication name but no dose",
      "The order includes the patient’s name, route, frequency, and signature",
      "The order says 'take as directed' with no frequency",
      "The order was written for PO medication in a patient receiving medications only by feeding tube",
      "The nurse disagrees with the drug choice but the order is complete",
      "The order has no date or time written"
    ],
    correct: [0,2,3,5],
    rationale: {
      whyCorrect: "This question combines legal order components with route safety. Missing dose, missing frequency, route mismatch, and missing date/time all require clarification because they create unsafe or incomplete orders.",
      whyWrong: [
        "Correct. A dose is required for a complete order.",
        "This order contains the listed required elements and does not, by itself, require clarification.",
        "Correct. Frequency must be clear.",
        "Correct. The route must match how the medication can actually be given.",
        "The nurse can question an order, but disagreement alone does not make a complete order automatically invalid. The stem asks which findings require clarification based on source-based completeness and safety issues.",
        "Correct. Date and time are required components."
      ],
      tip: "For SATA, separate 'I do not like it' from 'I cannot safely carry it out.'"
    }
  },
  {
    id: 4,
    section: "Pharmacology / Med Admin",
    type: "Multiple Choice",
    question: "The nurse reviews preadministration data before giving a renally excreted medication. Which finding most strongly supports contacting the provider about possible dosage adjustment?",
    options: [
      "BUN 18 mg/dL in a patient with no urinary complaints",
      "Creatinine 2.1 mg/dL in an older adult receiving the drug routinely",
      "A patient report of mild nausea after the previous dose",
      "A trough level scheduled for 30 minutes before the next dose"
    ],
    correct: [1],
    rationale: {
      whyCorrect: "Every answer contains something relevant, but the best answer is the elevated creatinine. The source emphasizes creatinine as a stronger indicator of renal impairment than BUN. A drug primarily excreted by the kidneys may accumulate and become toxic when renal clearance falls. This integrates lab interpretation with medication safety.",
      whyWrong: [
        "This BUN alone is not the strongest indicator of reduced renal clearance.",
        "Correct.",
        "Mild nausea may be a side effect, but it does not more strongly signal the need for dose adjustment than impaired renal function does.",
        "This is an appropriate monitoring plan, not a problem requiring provider contact."
      ],
      tip: "If the stem mentions kidneys and dose safety, creatinine usually matters more than vague symptoms."
    }
  },
  {
    id: 5,
    section: "Pharmacology / Med Admin",
    type: "Clinical Scenario",
    question: "A patient develops bronchospasm, wheezing, and hypotension minutes after an IV antibiotic is started. Which nursing interpretation is best?",
    options: [
      "The patient is experiencing a common predictable side effect",
      "The patient is likely having an idiosyncratic reaction that can be monitored",
      "The patient is showing signs of a serious allergic response consistent with anaphylaxis",
      "The patient is anxious about the IV medication and should be reassured"
    ],
    correct: [2],
    rationale: {
      whyCorrect: "Several options may appear plausible because many reactions can happen after medication administration, but airway involvement plus hypotension most strongly indicates anaphylaxis. This is not a mild side effect or simple anxiety. The question combines reaction classification with ABC prioritization.",
      whyWrong: [
        "A predictable side effect does not best fit severe airway and circulatory compromise.",
        "An idiosyncratic reaction is unusual, but the stem specifically points to a life-threatening allergic picture.",
        "Anxiety does not adequately explain bronchospasm with hypotension after drug exposure."
      ],
      tip: "When an answer choice names the most dangerous pattern that matches the clues, that is often the best answer."
    }
  },
  {
    id: 6,
    section: "Pharmacology / Med Admin",
    type: "Multiple Choice",
    question: "A nurse is teaching a student about serum drug monitoring. Which explanation best compares peak and trough levels?",
    options: [
      "Peak and trough levels are both drawn before a dose to assess baseline drug exposure",
      "A peak reflects the highest concentration after administration, while a trough reflects the lowest concentration before the next dose",
      "A trough is only needed for oral drugs, while a peak is only needed for IV drugs",
      "Peak and trough levels are mainly used to evaluate patient adherence rather than safety"
    ],
    correct: [1],
    rationale: {
      whyCorrect: "This is the most complete and accurate comparison. The question is harder because several choices use familiar monitoring language, but only one correctly matches both timing and purpose. The source specifically describes trough timing before the next dose and peak timing after administration.",
      whyWrong: [
        "This incorrectly places both levels before a dose.",
        "Correct.",
        "The source does not limit monitoring this way.",
        "These levels are used to support safe and therapeutic dosing, not mainly to measure adherence."
      ],
      tip: "On monitoring questions, match the timing words first: after dose versus before next dose."
    }
  },
  {
    id: 7,
    section: "Pharmacology / Med Admin",
    type: "Multiple Choice",
    question: "A patient taking high-dose aspirin reports ringing in the ears, dizziness, and difficulty with balance. Which conclusion is best?",
    options: [
      "The patient is most likely experiencing hepatotoxicity and needs liver monitoring",
      "The patient is showing likely ototoxicity associated with the medication",
      "The patient is experiencing an expected therapeutic effect of aspirin",
      "The patient is developing orthostatic hypotension from immobility"
    ],
    correct: [1],
    rationale: {
      whyCorrect: "All the distractors name real concepts from the course, which makes the question harder. The best answer is ototoxicity because the symptoms center on hearing and balance changes, and aspirin is listed as a possible cause in the source.",
      whyWrong: [
        "Hepatotoxicity does not best match ear and balance symptoms.",
        "Correct.",
        "These symptoms are adverse, not therapeutic.",
        "Orthostatic hypotension may cause dizziness, but it does not explain tinnitus or balance changes in this medication context."
      ],
      tip: "When a drug question includes body-system clues, trust the system-specific symptoms."
    }
  },
  {
    id: 8,
    section: "Pharmacology / Med Admin",
    type: "Multiple Choice",
    question: "Which patient is at greatest risk for medication toxicity based on the source principles?",
    options: [
      "A patient taking a drug with a narrow therapeutic index who has changing renal function",
      "A patient taking acetaminophen who asks for more education about the dose schedule",
      "A patient receiving a routine medication with a wide therapeutic index",
      "A patient reporting that a medication tastes unpleasant"
    ],
    correct: [0],
    rationale: {
      whyCorrect: "This answer combines two major risk factors: a narrow therapeutic index and impaired drug clearance. Either factor matters; together they create the highest risk for toxicity. The question integrates pharmacokinetic risk with therapeutic-index concepts.",
      whyWrong: [
        "Correct.",
        "This patient needs teaching, but not necessarily immediate toxicity management.",
        "A wide therapeutic index means there is more room between therapeutic and toxic levels.",
        "Unpleasant taste alone does not suggest toxicity."
      ],
      tip: "The hardest questions often stack two moderate risks into one best-answer option."
    }
  },

  {
    id: 9,
    section: "Analgesics",
    type: "Priority",
    question: "A nurse is deciding whether to administer a PRN opioid. Which assessment finding should most strongly influence the nurse to hold the medication and contact the provider?",
    options: [
      "Pain rating 8/10 after turning and repositioning",
      "Respiratory rate of 10/min with increasing drowsiness",
      "Nausea after the last opioid dose",
      "The patient asks whether the medication may cause constipation"
    ],
    correct: [1],
    rationale: {
      whyCorrect: "All four findings matter in opioid care, but the best answer is the low respiratory rate with increasing sedation because it signals possible respiratory depression. This integrates analgesic administration with ABC prioritization. The source specifically directs the nurse to notify the provider if respirations are below 12 before opioid administration.",
      whyWrong: [
        "Severe pain matters, but breathing still comes first.",
        "Nausea is relevant and should be managed, but it is not more urgent than respiratory compromise.",
        "Constipation teaching is appropriate, but not priority over airway and breathing concerns."
      ],
      tip: "On opioid questions, the most dangerous finding usually beats the most uncomfortable one."
    }
  },
  {
    id: 10,
    section: "Analgesics",
    type: "SATA",
    question: "The nurse is planning care for a patient receiving acetaminophen and NSAIDs for multimodal analgesia. Which points are accurate? Select all that apply.",
    options: [
      "Acetaminophen can cause hepatotoxicity if used above recommended dosing or too long",
      "NSAIDs can mask signs of infection",
      "NSAIDs are preferred for patients with bleeding disorders",
      "Using drugs from different classes may improve pain control while reducing reliance on a single agent",
      "All NSAIDs, including aspirin, increase myocardial infarction risk in the same way",
      "The maximum adult acetaminophen dose in the source is 4 g/day"
    ],
    correct: [0,1,3,5],
    rationale: {
      whyCorrect: "This item combines multimodal analgesia with nonopioid safety. The correct options reflect key source points: acetaminophen hepatotoxicity risk, NSAIDs masking infection, multimodal benefit, and the 4 g/day adult maximum listed in the notes.",
      whyWrong: [
        "Correct.",
        "Correct.",
        "Incorrect. NSAIDs are not preferred with bleeding disorders because they can interfere with platelet function.",
        "Correct.",
        "Incorrect. The source states all NSAIDs except aspirin increase risk of MI or stroke.",
        "Correct."
      ],
      tip: "Hard SATA often mixes one concept set with another. Read each line as its own mini true/false question."
    }
  },
  {
    id: 11,
    section: "Analgesics",
    type: "Clinical Scenario",
    question: "A patient receives a new fentanyl patch and reports severe pain 2 hours later. Which nursing interpretation is best?",
    options: [
      "The patch is clearly ineffective and should be doubled immediately",
      "Transdermal fentanyl may require several hours to reach therapeutic levels, so prescribed short-acting analgesics may still be needed",
      "The patient is showing drug-seeking behavior because the patch has already reached full effect",
      "The pain proves the patient is not opioid tolerant"
    ],
    correct: [1],
    rationale: {
      whyCorrect: "This option is best because it integrates route-based onset with safe pain management. The source states fentanyl patches may take several hours to reach therapeutic levels, so another prescribed analgesic may still be needed during that period. Several distractors are tempting because they sound decisive, but they are not the safest or most source-supported interpretation.",
      whyWrong: [
        "Doubling a patch without an order is dangerous and can lead to overdose when absorption increases.",
        "The stem does not support labeling the patient as drug-seeking.",
        "Tolerance status is not the best explanation for pain so soon after a new patch."
      ],
      tip: "When a stem tests route timing, choose the answer that explains onset before jumping to judgment or dose escalation."
    }
  },
  {
    id: 12,
    section: "Analgesics",
    type: "Multiple Choice",
    question: "A patient physically dependent on opioid agonists receives naloxone and then develops abdominal cramping, vomiting, and severe pain. Which explanation is best?",
    options: [
      "Naloxone can precipitate abstinence symptoms while also reversing analgesia",
      "Naloxone is causing an allergic reaction to the opioid",
      "The opioid dose was too low to begin with",
      "The findings show that naloxone has a longer half-life than the opioid"
    ],
    correct: [0],
    rationale: {
      whyCorrect: "This is the best integrated answer because it explains both the return of pain and the withdrawal-type symptoms. The source notes that naloxone can precipitate abstinence syndrome in dependent patients and that pain often returns when the opioid effect is reversed.",
      whyWrong: [
        "Correct.",
        "These symptoms are better explained by opioid reversal than by an allergy.",
        "The question focuses on the effect of naloxone, not inadequate prior dosing.",
        "The source highlights the opposite concern: the opioid may outlast naloxone, so repeat naloxone can be needed."
      ],
      tip: "Look for the answer choice that explains the whole pattern, not just one symptom."
    }
  },
  {
    id: 13,
    section: "Analgesics",
    type: "Multiple Choice",
    question: "Which statement about opioid agonist-antagonists is most accurate?",
    options: [
      "They provide stronger analgesia and more respiratory depression than pure agonists",
      "They have lower abuse potential and less analgesic effect than pure opioid agonists",
      "They eliminate the need for respiratory assessment because their safety profile is higher",
      "They are primarily used to reverse overdose in the same way as naloxone"
    ],
    correct: [1],
    rationale: {
      whyCorrect: "This answer best matches the source: opioid agonist-antagonists have lower abuse potential, less respiratory depression, and less analgesic effect than pure agonists. The question is harder because several distractors exaggerate true ideas into false absolutes.",
      whyWrong: [
        "This reverses the source information.",
        "Correct.",
        "A safer profile does not remove the need for respiratory assessment.",
        "They are not the primary reversal agents described for opioid overdose."
      ],
      tip: "Watch for answer choices that change 'less' into 'none' or 'more.'"
    }
  },
  {
    id: 14,
    section: "Analgesics",
    type: "Priority",
    question: "The nurse is caring for four patients receiving analgesics. Which patient should be assessed first?",
    options: [
      "A patient with chronic pain who wants the next scheduled opioid",
      "A patient who received an opioid 20 minutes ago and is increasingly difficult to arouse",
      "A patient whose NSAID has not relieved joint pain yet",
      "A patient asking whether acetaminophen should be taken with food"
    ],
    correct: [1],
    rationale: {
      whyCorrect: "Every patient needs nursing attention, but the increasingly difficult-to-arouse patient is most urgent because sedation may precede respiratory compromise. This question combines medication monitoring, safety, and ABC prioritization.",
      whyWrong: [
        "Pain matters, but possible opioid toxicity is more urgent.",
        "Unrelieved pain matters but is not the top priority over declining responsiveness.",
        "Teaching can wait until a potentially unstable patient is assessed."
      ],
      tip: "When all answers are reasonable, unstable or potentially unstable usually wins."
    }
  },

  {
    id: 15,
    section: "Immobility",
    type: "Multiple Choice",
    question: "A patient on prolonged bed rest becomes dizzy and weak when moving from lying to standing. Which explanation is best?",
    options: [
      "Atelectasis decreases blood flow to the brain during position changes",
      "Orthostatic hypotension develops because immobility impairs normal vasoconstrictive adjustment",
      "Venous thrombosis always causes dizziness before other symptoms appear",
      "Hypostatic pneumonia is reducing cerebral oxygenation during ambulation"
    ],
    correct: [1],
    rationale: {
      whyCorrect: "This is the best answer because it directly links a known immobility complication with the trigger in the stem: position change. The question is harder because all distractors mention real immobility complications, but only orthostatic hypotension best explains dizziness immediately after standing.",
      whyWrong: [
        "Atelectasis is a respiratory complication but does not best explain this position-dependent pattern.",
        "Venous thrombosis does not always present this way and is not the best fit for the question.",
        "Hypostatic pneumonia is a respiratory infection pattern, not the best explanation for faintness with standing."
      ],
      tip: "If the symptom appears right after a position change, give extra weight to orthostatic problems."
    }
  },
  {
    id: 16,
    section: "Immobility",
    type: "SATA",
    question: "Which findings are most consistent with respiratory complications of prolonged immobility? Select all that apply.",
    options: [
      "Pooling of secretions",
      "Atelectasis",
      "Improved gas exchange",
      "Hypostatic pneumonia",
      "Decreased cough effectiveness",
      "Rapid strengthening of respiratory muscles"
    ],
    correct: [0,1,3,4],
    rationale: {
      whyCorrect: "This SATA combines pathophysiology with complications. Immobility reduces ventilation, weakens secretion clearance, decreases cough efficiency, and increases risk for atelectasis and hypostatic pneumonia.",
      whyWrong: [
        "Correct.",
        "Correct.",
        "Incorrect. Gas exchange is impaired, not improved.",
        "Correct.",
        "Correct.",
        "Incorrect. Immobility weakens rather than strengthens respiratory performance."
      ],
      tip: "For immobility, think shallow breathing in, secretions stay in."
    }
  },
  {
    id: 17,
    section: "Immobility",
    type: "Priority",
    question: "A patient with prolonged immobility suddenly develops chest pain and shortness of breath. Which conclusion should the nurse make first?",
    options: [
      "The patient is likely anxious about limited mobility",
      "The patient may have developed a pulmonary embolism related to venous thrombosis",
      "The patient is showing a normal effect of deconditioning",
      "The patient probably has constipation with diaphragmatic pressure"
    ],
    correct: [1],
    rationale: {
      whyCorrect: "This answer best integrates immobility-related venous stasis with an acute cardiopulmonary emergency. Sudden chest pain and shortness of breath are major clues that a clot may have embolized to the lungs.",
      whyWrong: [
        "Anxiety may cause distress, but it should not be assumed when a life-threatening explanation fits better.",
        "Deconditioning is not the best explanation for an abrupt potentially unstable event.",
        "Constipation does not best explain this sudden symptom cluster."
      ],
      tip: "In priority questions, choose the answer that could kill the patient first if missed."
    }
  },
  {
    id: 18,
    section: "Immobility",
    type: "Clinical Scenario",
    question: "The nurse is teaching a family member about the consequences of bed rest. Which statement shows the best understanding?",
    options: [
      "The biggest concern is only loss of muscle strength; the other body systems are less affected",
      "Immobility can lead to contractures, bone demineralization, constipation, and venous stasis",
      "Keeping the patient completely still helps prevent most complications of immobility",
      "If the patient is not short of breath, immobility complications are unlikely"
    ],
    correct: [1],
    rationale: {
      whyCorrect: "This answer is best because it combines multiple body-system effects of immobility. Your professor’s style of combining objectives means the best answer often covers more than one true consequence. The source describes musculoskeletal, GI, and cardiovascular complications together.",
      whyWrong: [
        "Immobility affects many systems, not just muscles.",
        "Greater immobility worsens rather than prevents complications.",
        "Absence of shortness of breath does not rule out other major complications."
      ],
      tip: "When objectives are combined, the best answer often captures the widest correct clinical picture."
    }
  },
  {
    id: 19,
    section: "Immobility",
    type: "Multiple Choice",
    question: "Which nursing action best reduces the risk of venous stasis in an immobile patient?",
    options: [
      "Encouraging movement and activity as tolerated",
      "Keeping the patient flat to avoid dizziness",
      "Limiting leg movement to prevent clot dislodgment",
      "Restricting fluids to reduce edema formation"
    ],
    correct: [0],
    rationale: {
      whyCorrect: "This is the best answer because mobility supports venous return through muscle activity. The distractors sound cautious, but they actually worsen immobility-related risk.",
      whyWrong: [
        "Correct.",
        "Extended flat bed rest contributes to complications rather than preventing them.",
        "Routine prevention does not involve further immobilizing the legs.",
        "Fluid restriction is not the best strategy for preventing venous stasis."
      ],
      tip: "If the body can move safely, movement is usually protective."
    }
  },
  {
    id: 20,
    section: "Immobility",
    type: "Multiple Choice",
    question: "Which teaching point best reflects proper body mechanics during patient handling?",
    options: [
      "Twist at the waist so the feet can stay in place",
      "Use a broad base of support and face the direction of movement",
      "Keep the feet together to improve balance",
      "Lift the patient whenever possible to reduce friction"
    ],
    correct: [1],
    rationale: {
      whyCorrect: "This answer combines the major body-mechanics principles from the source: broad base of support, balance, and avoiding twisting. The best-answer style here requires recognizing that some options sound practical but are less safe.",
      whyWrong: [
        "Twisting increases injury risk.",
        "Feet together narrows the base of support and decreases stability.",
        "Unnecessary lifting increases strain; sliding or assistive devices are often safer."
      ],
      tip: "Broad base and face movement direction is the safer pairing."
    }
  },

  {
    id: 21,
    section: "Wound",
    type: "Clinical Scenario",
    question: "A postoperative wound shows thick green drainage, increasing warmth, redness, swelling, and pain. Which interpretation is best?",
    options: [
      "The wound is progressing through the normal inflammatory phase",
      "The wound shows purulent drainage and likely infection",
      "The wound is healing by primary intention with expected drainage",
      "The wound is only demonstrating serous drainage from tissue hydration"
    ],
    correct: [1],
    rationale: {
      whyCorrect: "Several options mention real wound concepts, but the best answer is infection. Purulent drainage plus local inflammatory signs strongly supports wound infection rather than uncomplicated healing. This integrates drainage identification with assessment of infection signs.",
      whyWrong: [
        "Normal inflammation does not best explain thick green drainage and worsening local signs.",
        "Primary intention describes edge approximation, not infected drainage findings.",
        "Serous drainage is clear and watery, not thick, green, and odorous."
      ],
      tip: "When the wound looks worse and the drainage looks infected, do not let normal-healing language distract you."
    }
  },
  {
    id: 22,
    section: "Wound",
    type: "SATA",
    question: "Which findings would make the nurse more suspicious of wound infection rather than uncomplicated healing? Select all that apply.",
    options: [
      "Purulent drainage",
      "Increasing wound pain",
      "Clean, approximated wound edges",
      "Erythema and swelling",
      "Elevated temperature",
      "Increased WBC count"
    ],
    correct: [0,1,3,4,5],
    rationale: {
      whyCorrect: "This item combines local and systemic evidence of infection. Purulent drainage, worsening pain, redness, swelling, fever, and elevated WBC count support infection. Clean, approximated edges suggest more normal healing.",
      whyWrong: [
        "Correct.",
        "Correct.",
        "Incorrect. This finding supports healing rather than infection.",
        "Correct.",
        "Correct.",
        "Correct."
      ],
      tip: "On wound questions, pair what you see locally with what the body is doing systemically."
    }
  },
  {
    id: 23,
    section: "Wound",
    type: "Clinical Scenario",
    question: "On postoperative day 5, a patient states that something in the incision 'gave way,' and the nurse notes a sudden increase in serosanguineous drainage. Which conclusion is best?",
    options: [
      "The patient is demonstrating expected wound maturation",
      "The patient may be developing dehiscence",
      "The patient is healing by tertiary intention",
      "The patient is showing normal drain function"
    ],
    correct: [1],
    rationale: {
      whyCorrect: "This best-answer item combines timing with assessment clues. A sudden increase in serosanguineous drainage around postoperative days 4 to 5 plus the patient’s report that something gave way strongly suggests dehiscence.",
      whyWrong: [
        "The timing and abrupt change are concerning rather than expected.",
        "Tertiary intention is a wound-healing strategy, not the best explanation for acute separation clues.",
        "Nothing in the stem says a drain is causing the finding, and the classic clues point elsewhere."
      ],
      tip: "Professor-style questions often reward matching several clues together, not just one word."
    }
  },
  {
    id: 24,
    section: "Wound",
    type: "Priority",
    question: "A nurse sees loops of bowel protruding from a postoperative abdominal wound. What action is best to take first?",
    options: [
      "Cover the protruding organs with sterile saline-soaked dressings",
      "Attempt to gently replace the bowel to reduce tissue drying",
      "Apply firm pressure over the site and reinforce the dressing",
      "Place the patient upright to improve visualization of the wound"
    ],
    correct: [0],
    rationale: {
      whyCorrect: "All options are action statements, which makes this feel harder, but only one is correct and safe. Evisceration requires moist sterile saline dressings to protect exposed tissue while further help is obtained. Reinsertion is not done by the nurse.",
      whyWrong: [
        "Correct.",
        "The nurse should not push exposed organs back into the wound.",
        "Firm pressure can worsen injury and is not the priority action.",
        "An upright position increases abdominal strain rather than protecting the wound."
      ],
      tip: "In emergency wound questions, protect tissue first and do not improvise invasive correction."
    }
  },
  {
    id: 25,
    section: "Wound",
    type: "SATA",
    question: "Which patients are at increased risk for dehiscence or evisceration? Select all that apply.",
    options: [
      "A patient with obesity after abdominal surgery",
      "A patient with wound infection",
      "A patient with persistent coughing and vomiting",
      "A patient with malnutrition or dehydration",
      "A patient with a well-healed superficial paper cut",
      "A patient with excessive abdominal strain"
    ],
    correct: [0,1,2,3,5],
    rationale: {
      whyCorrect: "This SATA combines surgical, nutritional, infectious, and mechanical risk factors. The source lists obesity, abdominal surgery, infection, coughing, vomiting, dehydration, malnutrition, and straining as risk factors for dehiscence/evisceration.",
      whyWrong: [
        "Correct.",
        "Correct.",
        "Correct.",
        "Correct.",
        "A healed superficial paper cut is not the kind of wound at major risk for these complications.",
        "Correct."
      ],
      tip: "Think weak healing plus high pressure. That combination raises separation risk."
    }
  },
  {
    id: 26,
    section: "Wound",
    type: "Multiple Choice",
    question: "A wound contains black eschar. Which management principle from the notes is most appropriate?",
    options: [
      "Debride the wound because black tissue indicates necrosis",
      "Massage the wound bed to improve blood flow",
      "Leave the eschar open to air until red tissue forms underneath",
      "Apply pressure to remove necrotic drainage manually"
    ],
    correct: [0],
    rationale: {
      whyCorrect: "This answer best matches the color-care principle in the source. Black tissue indicates eschar or necrotic tissue, and the notes associate this finding with debridement. The distractors sound active but are not the correct source-based intervention.",
      whyWrong: [
        "Correct.",
        "Massage is not the indicated intervention for eschar.",
        "Leaving necrotic tissue untreated does not reflect the source recommendation.",
        "Manual pressure to force tissue or drainage out is not appropriate wound care."
      ],
      tip: "Black wound tissue should make you think necrosis first, then debridement."
    }
  },
  {
    id: 27,
    section: "Wound",
    type: "Multiple Choice",
    question: "Which dressing choice best matches a wound that is dry, needs rehydration, and should undergo autolytic debridement?",
    options: [
      "Alginate dressing",
      "Hydrogel dressing",
      "Vacuum-assisted closure",
      "Collagen dressing"
    ],
    correct: [1],
    rationale: {
      whyCorrect: "This item tests matching wound characteristics to the best dressing. Hydrogels are mostly water, help rehydrate tissue, and support autolytic debridement. The other options may be reasonable in other contexts, but this is the best fit for the stem.",
      whyWrong: [
        "Alginate is more useful for absorbing exudate than rehydrating a dry wound.",
        "Vacuum-assisted closure uses negative pressure and is not the best first match for this description.",
        "Collagen promotes healing but is not the mostly-water rehydrating dressing described."
      ],
      tip: "Match the wound need to the dressing job. Dry wound plus rehydrate points to hydrogel."
    }
  },
  {
    id: 28,
    section: "Wound",
    type: "Clinical Scenario",
    question: "The nurse assesses a chronic wound and notes a nonhealing wound, exudate, red bleeding tissue, debris, and odor. Which source mnemonic best matches this pattern?",
    options: [
      "STONEES",
      "NERDS",
      "ABCs",
      "ROM"
    ],
    correct: [1],
    rationale: {
      whyCorrect: "This best-answer item requires careful discrimination between two wound mnemonics. NERDS stands for Nonhealing wound, Exudative wound, Red and bleeding wound, Debris, and Smell. The clues line up directly with that set.",
      whyWrong: [
        "STONEES is a different wound-infection mnemonic and is not the best fit for the exact list presented.",
        "ABCs is a priority framework, not a wound mnemonic.",
        "ROM refers to range of motion."
      ],
      tip: "When two terms look familiar, match the letters back to the actual clues in the stem."
    }
  },
  {
    id: 29,
    section: "Wound",
    type: "Multiple Choice",
    question: "Which statement best explains the purpose of a wound drain?",
    options: [
      "It proves the wound is infected and must stay open",
      "It promotes drainage, lowers abscess risk, and supports wound healing",
      "It eliminates the need for ongoing wound assessment",
      "It is mainly used to expose the wound to air so bacteria cannot grow"
    ],
    correct: [1],
    rationale: {
      whyCorrect: "This is the best integrated answer because it captures the main purpose of a drain and reinforces why drainage assessment still matters. In hard best-answer questions, the strongest option often includes several linked truths rather than one isolated fact.",
      whyWrong: [
        "A drain does not automatically prove infection.",
        "Drains increase the need for assessment of amount, color, odor, and consistency.",
        "The purpose is not simply air exposure."
      ],
      tip: "The best answer often sounds the most complete without adding unsafe assumptions."
    }
  },
  {
    id: 30,
    section: "Wound",
    type: "Priority",
    question: "A patient has an incision with moderate serosanguineous drainage, increasing pain, fever, and a rising WBC count. Which nursing judgment is best?",
    options: [
      "The drainage is automatically normal because serosanguineous fluid can occur in healing wounds",
      "The systemic findings increase concern for wound infection despite the drainage not being purulent",
      "The patient is healing by primary intention without complication",
      "The main concern is only fluid loss from the dressing"
    ],
    correct: [1],
    rationale: {
      whyCorrect: "This is more difficult because one clue alone could mislead you. Serosanguineous drainage can occur in healing, but when it is combined with increasing pain, fever, and rising WBC count, the overall picture is more concerning for infection or complication. This is exactly the kind of combined-objective reasoning professors like to test.",
      whyWrong: [
        "The answer overfocuses on one clue and ignores the more concerning systemic findings.",
        "The stem includes signs that should prevent the nurse from assuming uncomplicated healing.",
        "Fluid loss is not the best interpretation of the complete clinical picture."
      ],
      tip: "Do not anchor on one familiar clue if the rest of the stem points somewhere more serious."
    }
  },

  {
    id: 31,
    section: "Rest / Sleep",
    type: "Multiple Choice",
    question: "A nurse is teaching a patient about sleep stages. Which statement is most accurate?",
    options: [
      "REM sleep is mainly a light transition phase that lasts only a few minutes",
      "REM sleep is associated with vivid dreaming and loss of skeletal muscle tone",
      "Stage 3 NREM is the stage in which most vivid dreaming occurs",
      "NREM sleep is marked by highly variable vital signs and muscle atonia"
    ],
    correct: [1],
    rationale: {
      whyCorrect: "This is the best answer because it accurately captures the key REM features from the source. The distractors borrow traits from other stages to make them tempting, but only one option correctly pairs dreaming with muscle atonia.",
      whyWrong: [
        "This describes Stage 1 NREM more than REM.",
        "Vivid dreaming is more strongly associated with REM.",
        "Variable vital signs and muscle atonia are not NREM hallmarks in the source."
      ],
      tip: "Pair the signature clue with the stage: dreaming plus muscle atonia points to REM."
    }
  },
  {
    id: 32,
    section: "Rest / Sleep",
    type: "Clinical Scenario",
    question: "A patient says, 'I fall asleep late, wake up too early, and never feel refreshed.' Which interpretation is best?",
    options: [
      "The pattern is most consistent with insomnia",
      "The pattern proves narcolepsy",
      "The pattern most strongly indicates sleep apnea only",
      "The pattern is normal for hospitalized adults"
    ],
    correct: [0],
    rationale: {
      whyCorrect: "This best-answer item combines several insomnia features from the source: difficulty initiating sleep, early awakening, and nonrestorative sleep. The wrong options each focus too narrowly or make an unsupported conclusion.",
      whyWrong: [
        "Correct.",
        "Narcolepsy involves sudden uncontrollable sleep attacks, which are not described here.",
        "Sleep apnea involves repeated breathing cessation and oxygen desaturation, which are not directly stated in the stem.",
        "Poor sleep may occur in the hospital, but the symptom pattern still best fits insomnia."
      ],
      tip: "When the stem gives you the actual definition pattern, trust it."
    }
  },
  {
    id: 33,
    section: "Rest / Sleep",
    type: "Priority",
    question: "A hospitalized patient reports poor sleep. Which intervention is best to implement first?",
    options: [
      "Request a sedative-hypnotic immediately so the patient can rest",
      "Promote a quiet environment and align care with the patient’s usual bedtime routine when possible",
      "Encourage caffeine in the evening to prevent fatigue-related headaches",
      "Increase fluid intake at bedtime to prevent overnight dehydration"
    ],
    correct: [1],
    rationale: {
      whyCorrect: "All four options are actions, but the best first step is nonpharmacologic sleep promotion. The source emphasizes bedtime routine, reduced disruption, and environmental comfort before medication. This integrates sleep hygiene with priority nursing care.",
      whyWrong: [
        "Medication may be considered later, but it is not the best first intervention from the source.",
        "Caffeine may worsen sleep.",
        "Extra fluids at bedtime can increase awakenings and disrupt sleep."
      ],
      tip: "For sleep questions, think routine and environment before medication unless the stem changes the priority."
    }
  },
  {
    id: 34,
    section: "Rest / Sleep",
    type: "SATA",
    question: "Which teaching points support healthy sleep hygiene? Select all that apply.",
    options: [
      "Exercise earlier in the evening rather than right before bed",
      "Keep a regular bedtime routine",
      "Limit alcohol, caffeine, and nicotine before bedtime",
      "Increase fluids immediately before sleep",
      "Create a comfortable sleep environment",
      "Use muscle relaxation when anxious"
    ],
    correct: [0,1,2,4,5],
    rationale: {
      whyCorrect: "This question combines several sleep-promoting behaviors from the source. Exercise earlier, consistent routine, limiting stimulants, comfort measures, and relaxation all support sleep hygiene.",
      whyWrong: [
        "Correct.",
        "Correct.",
        "Correct.",
        "Incorrect. Extra fluids before bed can increase sleep disruption.",
        "Correct.",
        "Correct."
      ],
      tip: "Sleep hygiene questions usually reward low stimulation, consistency, and comfort."
    }
  },

  {
    id: 35,
    section: "Mixed Integrated",
    type: "Priority",
    question: "Which patient should the nurse assess first?",
    options: [
      "A patient with an infected abdominal wound reporting increased pain and a temperature of 100.4°F",
      "A patient on bed rest who becomes dizzy when standing for the first time",
      "A patient who received an opioid 15 minutes ago and is now difficult to arouse with respirations of 10/min",
      "A patient asking whether a hydrogel dressing is used for dry wounds"
    ],
    correct: [2],
    rationale: {
      whyCorrect: "This item combines wound, immobility, analgesics, and teaching content. Every answer points to something real, but the opioid patient with declining responsiveness and low respirations is the most urgent because airway and breathing threats take priority. This is the exact kind of combined-objective best-answer reasoning your professor may use.",
      whyWrong: [
        "This patient likely needs evaluation for infection, but not before a potentially unstable airway/breathing problem.",
        "This likely reflects orthostatic hypotension and needs intervention, but it is not more urgent than possible opioid-induced respiratory depression.",
        "Teaching can wait until unstable issues are addressed."
      ],
      tip: "When objectives are mixed, use ABCs to cut through the noise."
    }
  },
  {
    id: 36,
    section: "Mixed Integrated",
    type: "Clinical Scenario",
    question: "A patient on prolonged bed rest after abdominal surgery has increasing wound pain, a rising WBC count, and suddenly reports shortness of breath. Which interpretation is best?",
    options: [
      "Only wound infection should be considered because the WBC count is elevated",
      "The patient may have more than one complication, including wound infection and an immobility-related pulmonary embolic event",
      "Shortness of breath is expected after surgery and does not need further thought if the wound is the main problem",
      "The symptoms are best explained by REM sleep deprivation"
    ],
    correct: [1],
    rationale: {
      whyCorrect: "This is a combined-objective question. The wound findings raise concern for infection, while sudden shortness of breath in a prolonged immobility context raises concern for pulmonary embolism. The best answer is the one that explains the full clinical picture rather than forcing only one diagnosis.",
      whyWrong: [
        "This answer is too narrow and ignores the acute cardiopulmonary red flag.",
        "Shortness of breath after immobility should not be minimized when embolic complications are possible.",
        "Sleep deprivation does not explain the integrated surgical, wound, and respiratory findings."
      ],
      tip: "The best answer may be the one broad enough to account for all the clues, not just the first clue you notice."
    }
  },
  {
    id: 37,
    section: "Mixed Integrated",
    type: "SATA",
    question: "The nurse is planning care for a postoperative immobile patient receiving opioids with an abdominal incision. Which assessments are highest priority based on the combined risks in the source material? Select all that apply.",
    options: [
      "Respiratory rate and level of sedation",
      "Wound drainage, approximation, and signs of infection",
      "Bowel function and constipation pattern",
      "Ability to stand quickly without dizziness",
      "Signs of venous stasis or thrombotic complications",
      "Whether the patient prefers the room lights left on at night"
    ],
    correct: [0,1,2,3,4],
    rationale: {
      whyCorrect: "This question combines analgesic, wound, and immobility objectives. Respiratory monitoring matters because of opioids, wound assessment matters after surgery, bowel function matters because of opioids and immobility, orthostatic symptoms matter because of bed rest, and venous stasis matters because of immobility. Room-light preference may matter for comfort but is not a highest-priority combined-risk assessment.",
      whyWrong: [
        "Correct.",
        "Correct.",
        "Correct.",
        "Correct.",
        "Correct.",
        "This may influence comfort, but it is not one of the highest priority combined-risk assessments in this postoperative context."
      ],
      tip: "On integrated SATA, ask: what could harm this patient because of the actual risk stack in the stem?"
    }
  },
  {
    id: 38,
    section: "Mixed Integrated",
    type: "Multiple Choice",
    question: "Which nursing intervention best addresses both immobility risk and wound-healing support in a postoperative patient?",
    options: [
      "Maintain strict bed rest to avoid tension on the incision",
      "Encourage activity as tolerated with safe body mechanics and careful wound monitoring",
      "Limit movement until all drainage has stopped completely",
      "Focus on sleep hygiene only because rest is the main factor in healing"
    ],
    correct: [1],
    rationale: {
      whyCorrect: "This option is the best because it combines two objectives instead of overprotecting one and ignoring the other. Activity as tolerated helps reduce immobility complications, while safe body mechanics and wound monitoring protect healing. The distractors all overvalue one concern while creating new risks.",
      whyWrong: [
        "Strict bed rest increases immobility complications and is not the best broad intervention unless specifically ordered.",
        "Waiting for all drainage to stop can prolong immobility unnecessarily.",
        "Sleep matters, but it does not replace mobility and wound-focused care."
      ],
      tip: "The best answer often balances competing priorities instead of choosing only one."
    }
  },
  {
    id: 39,
    section: "Mixed Integrated",
    type: "Case Study Item 1",
    question: "Case: A postoperative abdominal-surgery patient has been mostly on bed rest, is receiving opioid pain medication, and now has increasing wound pain, low-grade fever, and moderate serosanguineous drainage. Which assessment is the nurse’s best next step?",
    options: [
      "Assess the wound for approximation, color/amount of drainage, and signs of infection while also checking current respiratory status",
      "Assume the drainage is normal and wait for the next provider round",
      "Hold all pain medication permanently until the fever resolves",
      "Encourage the patient to ambulate alone immediately to improve circulation"
    ],
    correct: [0],
    rationale: {
      whyCorrect: "This is written in the style of a case-study item. The best answer integrates the major current risks: wound complication and opioid-related respiratory safety. Because the patient has multiple concerns, the best next step is a focused assessment that addresses both.",
      whyWrong: [
        "Correct.",
        "Waiting delays evaluation of possible complications.",
        "Permanently withholding analgesia is not the best next step and ignores the need for assessment and provider-guided management.",
        "Ambulation may help circulation, but not alone and not before assessing current stability and wound status."
      ],
      tip: "In case-style questions, pick the answer that gathers the most important missing clinical data safely."
    }
  },
  {
    id: 40,
    section: "Mixed Integrated",
    type: "Case Study Item 2",
    question: "The same patient becomes dizzy when standing and later says the incision felt like it 'pulled apart' after coughing. Which interpretation is best?",
    options: [
      "The patient may have both orthostatic hypotension from immobility and possible dehiscence related to wound stress",
      "The symptoms are best explained by normal postoperative weakness only",
      "Because the drainage is not purulent, dehiscence is impossible",
      "The coughing episode is unrelated to abdominal wound complications"
    ],
    correct: [0],
    rationale: {
      whyCorrect: "This is a higher-level integrated interpretation question. Dizziness with standing fits orthostatic hypotension, while the report that the incision pulled apart after coughing raises concern for dehiscence. The best answer recognizes that more than one complication may be developing.",
      whyWrong: [
        "Correct.",
        "This is too dismissive and ignores specific source-based clues.",
        "Purulence is not required for dehiscence to occur.",
        "Coughing can increase abdominal strain and contribute to wound separation."
      ],
      tip: "Professors love stems with two real problems hiding in one scenario."
    }
  },
  {
    id: 41,
    section: "Mixed Integrated",
    type: "Case Study Item 3",
    question: "The patient’s respirations are now 10/min after an opioid dose, and the patient is difficult to arouse. Which action is best?",
    options: [
      "Give the next opioid dose late and continue watching",
      "Notify the provider and treat this as a possible opioid-related respiratory safety issue",
      "Encourage deep breathing and reassess in an hour",
      "Document expected postoperative drowsiness"
    ],
    correct: [1],
    rationale: {
      whyCorrect: "This case item pulls the analgesic objective into the broader scenario. Low respirations with difficult arousal after an opioid should be treated as a priority respiratory safety problem. The best answer is the one that acts on the ABC concern.",
      whyWrong: [
        "Delaying the next dose is not enough when current safety is already in question.",
        "Deep breathing alone is not the best response to possible opioid-induced respiratory depression.",
        "This finding should not be minimized as expected drowsiness."
      ],
      tip: "Do not normalize dangerous sedation findings just because the patient is postoperative."
    }
  },
  {
    id: 42,
    section: "Mixed Integrated",
    type: "Case Study Item 4",
    question: "Which nursing outcome would best show that the current plan of care is working for this patient?",
    options: [
      "The patient has improved respiratory status, no new orthostatic symptoms, and the wound shows no worsening signs of separation or infection",
      "The patient says the room is quieter at night",
      "The patient receives every PRN pain medication on time",
      "The patient remains in bed most of the day to protect the incision"
    ],
    correct: [0],
    rationale: {
      whyCorrect: "This outcome combines the main active risks in the scenario: opioid respiratory safety, immobility complications, and wound stability. A professor-style question often makes the best answer the one that reflects several objectives at once rather than only one narrow success marker.",
      whyWrong: [
        "Correct.",
        "A quieter room may help comfort but does not best evaluate the major priorities in the case.",
        "Receiving all PRN pain medications does not, by itself, prove safe or effective overall care.",
        "Remaining in bed most of the day worsens immobility-related risk."
      ],
      tip: "For outcomes, choose the answer that proves the biggest risks are improving."
    }
  },
  {
    id: 43,
    section: "Pharmacology / Med Admin",
    type: "Multiple Choice",
    question: "A medication has a high first-pass effect. Which interpretation is best?",
    options: [
      "More of the oral medication reaches circulation unchanged",
      "A significant portion of the oral medication is metabolized before reaching systemic circulation",
      "The medication is absorbed only through the skin",
      "The medication does not require liver metabolism"
    ],
    correct: [1],
    rationale: {
      whyCorrect: "A first-pass effect means the liver metabolizes a portion of the drug before it reaches systemic circulation, which lowers bioavailability. The best answer connects the route and the pharmacokinetic consequence.",
      whyWrong: [
        "This describes higher bioavailability, not a high first-pass effect.",
        "Skin absorption is unrelated to this concept.",
        "A first-pass effect specifically involves liver metabolism."
      ],
      tip: "First-pass usually means less active drug makes it into circulation after oral administration."
    }
  },
  {
    id: 44,
    section: "Pharmacology / Med Admin",
    type: "Clinical Scenario",
    question: "An older adult with low albumin is prescribed a highly protein-bound medication. Which nursing concern is best?",
    options: [
      "Less free drug will be available to act",
      "More unbound drug may circulate, increasing toxicity risk",
      "The drug will bypass the kidneys",
      "The medication will have no therapeutic effect"
    ],
    correct: [1],
    rationale: {
      whyCorrect: "Highly protein-bound medications can leave more free drug in circulation when protein levels are low, increasing the risk of stronger effects or toxicity. This is a classic combined lab-and-pharmacology question.",
      whyWrong: [
        "Low albumin causes more free drug, not less.",
        "Protein binding does not mean the drug bypasses renal excretion.",
        "The effect is not absent; it may actually be stronger."
      ],
      tip: "Less protein binding means more free active drug."
    }
  },
  {
    id: 45,
    section: "Pharmacology / Med Admin",
    type: "Multiple Choice",
    question: "Which order type should the nurse interpret as a medication to be given only one time and immediately?",
    options: [
      "Standing order",
      "PRN order",
      "STAT order",
      "Routine order"
    ],
    correct: [2],
    rationale: {
      whyCorrect: "A STAT order is carried out immediately and one time. The hard part is distinguishing it from other common order types that may also seem time related.",
      whyWrong: [
        "Standing orders remain in effect until changed or discontinued.",
        "PRN means as needed, not automatically immediate.",
        "Routine orders are scheduled, not immediate one-time orders."
      ],
      tip: "STAT means now. PRN means if needed."
    }
  },
  {
    id: 46,
    section: "Pharmacology / Med Admin",
    type: "Priority",
    question: "Which medication situation should the nurse clarify first?",
    options: [
      "A patient refuses a scheduled medication after teaching and states, 'I still do not want it.'",
      "A medication label is difficult to read during the third check before administration",
      "A patient asks whether a routine medication can be taken with applesauce",
      "A patient says the medication was taken at home at a different time"
    ],
    correct: [1],
    rationale: {
      whyCorrect: "A difficult-to-read label directly threatens the nurse’s ability to verify the correct medication safely. Refusal and patient questions matter, but the unreadable label creates an immediate administration safety barrier.",
      whyWrong: [
        "Refusal should be respected and documented, but it is not the most urgent safety threat in this stem.",
        "This can be addressed after safe identification of medications.",
        "Home schedules matter, but not before immediate medication verification issues."
      ],
      tip: "If you cannot verify the medication, you cannot safely give it."
    }
  },
  {
    id: 47,
    section: "Pharmacology / Med Admin",
    type: "SATA",
    question: "Which findings are most consistent with nephrotoxicity from medication therapy? Select all that apply.",
    options: [
      "Decreased urine output",
      "Edema",
      "Increased blood pressure",
      "Tinnitus",
      "Creatinine elevation",
      "Bronchospasm"
    ],
    correct: [0,1,2,4],
    rationale: {
      whyCorrect: "The source links nephrotoxicity with fluid retention, reduced output, increased blood pressure, and abnormal kidney labs such as creatinine elevation. The question mixes in other adverse effects to test discrimination.",
      whyWrong: [
        "Correct.",
        "Correct.",
        "Correct.",
        "Tinnitus is more consistent with ototoxicity.",
        "Correct.",
        "Bronchospasm fits an allergic or anaphylactic pattern, not nephrotoxicity."
      ],
      tip: "Kidney toxicity often shows up as fluid problems plus lab problems."
    }
  },
  {
    id: 48,
    section: "Pharmacology / Med Admin",
    type: "Multiple Choice",
    question: "A provider prescribes a loading dose followed by smaller regular doses. Which rationale best explains the loading dose?",
    options: [
      "It prevents all side effects from the medication",
      "It helps the drug reach therapeutic levels more quickly",
      "It replaces the need for maintenance dosing",
      "It is used only for medications with wide therapeutic indexes"
    ],
    correct: [1],
    rationale: {
      whyCorrect: "A loading dose is used to rapidly achieve a therapeutic blood level. Maintenance doses then keep the drug within that range. The best answer explains purpose, not just naming the term.",
      whyWrong: [
        "Loading doses do not eliminate side effects.",
        "Maintenance dosing is still needed after the loading dose.",
        "This is not limited to wide therapeutic index drugs."
      ],
      tip: "Loading dose = get there fast. Maintenance dose = stay there."
    }
  },
  {
    id: 49,
    section: "Analgesics",
    type: "Multiple Choice",
    question: "Which statement best explains why PCA can improve pain management for some postoperative patients?",
    options: [
      "It lets the patient self-administer within prescribed limits when pain begins rather than waiting for severe pain",
      "It removes the need for any respiratory monitoring",
      "It automatically gives unlimited doses based on pain rating",
      "It is used only for patients who cannot understand instructions"
    ],
    correct: [0],
    rationale: {
      whyCorrect: "PCA allows patient-controlled dosing within safe programmed limits, which can treat pain sooner and more consistently. The distractors misuse absolutes to sound tempting.",
      whyWrong: [
        "Correct.",
        "Respiratory monitoring is still required.",
        "PCA is programmed with dose limits and lockout intervals.",
        "PCA requires understanding and participation, not the opposite."
      ],
      tip: "If an analgesic answer says 'no monitoring' or 'unlimited,' it is usually wrong."
    }
  },
  {
    id: 50,
    section: "Analgesics",
    type: "Clinical Scenario",
    question: "A patient taking NSAIDs for pain reports black stools and epigastric discomfort. Which nursing interpretation is best?",
    options: [
      "These are expected harmless effects of NSAID therapy",
      "These findings increase concern for GI irritation or bleeding related to NSAIDs",
      "This proves the patient has wound dehiscence",
      "These symptoms best fit REM rebound"
    ],
    correct: [1],
    rationale: {
      whyCorrect: "NSAIDs can irritate the GI tract and increase bleeding risk. Black stools and epigastric pain should raise concern for GI bleeding rather than being minimized.",
      whyWrong: [
        "These are not harmless findings.",
        "Correct.",
        "Wound dehiscence is unrelated to black stools.",
        "REM rebound does not explain GI bleeding signs."
      ],
      tip: "Dark stools plus NSAIDs should make you think GI bleed until proven otherwise."
    }
  },
  {
    id: 51,
    section: "Analgesics",
    type: "Priority",
    question: "Which patient teaching statement requires immediate correction?",
    options: [
      "I will call if my opioid makes me too sleepy or slow my breathing.",
      "I can take more acetaminophen as long as it is over-the-counter.",
      "I should ask before using alcohol with pain medicine.",
      "I may need bowel management if I take opioids regularly."
    ],
    correct: [1],
    rationale: {
      whyCorrect: "This statement is dangerous because acetaminophen toxicity can occur when doses exceed recommendations, even though it is available over the counter. The question tests safe teaching, not just drug facts.",
      whyWrong: [
        "This is appropriate teaching.",
        "Correct.",
        "This is appropriate safety teaching.",
        "This is appropriate opioid-related teaching."
      ],
      tip: "OTC does not mean harmless."
    }
  },
  {
    id: 52,
    section: "Analgesics",
    type: "SATA",
    question: "Which assessment findings should the nurse connect with possible opioid adverse effects? Select all that apply.",
    options: [
      "Decreased respiratory rate",
      "Increased sedation",
      "Constipation",
      "Rapid strengthening of cough",
      "Nausea",
      "Improved bowel motility"
    ],
    correct: [0,1,2,4],
    rationale: {
      whyCorrect: "The source highlights respiratory depression, sedation, constipation, and nausea as opioid-related concerns. The distractors flip those concepts into unrealistic opposites.",
      whyWrong: [
        "Correct.",
        "Correct.",
        "Correct.",
        "This is not an expected opioid adverse effect.",
        "Correct.",
        "Opioids decrease bowel motility, not improve it."
      ],
      tip: "Think opioids slow things down: breathing, bowel movement, and alertness."
    }
  },
  {
    id: 53,
    section: "Immobility",
    type: "Multiple Choice",
    question: "Which immobility-related change best explains why an older patient on bed rest may develop hypercalcemia?",
    options: [
      "Bone demineralization releases calcium into the bloodstream",
      "Improved kidney function retains calcium more efficiently",
      "Sleep deprivation causes increased intestinal calcium absorption",
      "Opioids directly produce bone growth"
    ],
    correct: [0],
    rationale: {
      whyCorrect: "Bone demineralization during immobility can release calcium from bone into circulation, contributing to hypercalcemia. The distractors either misstate body systems or invent unsupported mechanisms.",
      whyWrong: [
        "Correct.",
        "This is not the best explanation from the source.",
        "Sleep deprivation is not the source-based cause here.",
        "Opioids do not cause bone growth."
      ],
      tip: "Immobility weakens bone and can release calcium."
    }
  },
  {
    id: 54,
    section: "Immobility",
    type: "Clinical Scenario",
    question: "An immobile patient has calf warmth, swelling, and unilateral tenderness. Which nursing interpretation is best?",
    options: [
      "These are expected musculoskeletal changes from contracture",
      "These findings raise concern for venous thrombosis",
      "This is the normal result of safe ambulation",
      "This best reflects stage 3 sleep deprivation"
    ],
    correct: [1],
    rationale: {
      whyCorrect: "Warmth, swelling, and unilateral tenderness in an immobile patient are classic clues of venous thrombosis. The question tests whether the nurse can connect local limb findings with larger immobility risk.",
      whyWrong: [
        "Contractures do not best explain unilateral swelling and warmth.",
        "These are not normal post-activity findings in this context.",
        "Sleep deprivation does not explain localized calf findings."
      ],
      tip: "Unilateral leg changes plus immobility should make you think clot."
    }
  },
  {
    id: 55,
    section: "Immobility",
    type: "Priority",
    question: "Which nursing action is best for reducing both atelectasis risk and secretion pooling in an immobile patient?",
    options: [
      "Encourage effective repositioning and measures that promote deeper breathing and cough",
      "Keep the patient lying flat to conserve energy",
      "Restrict fluids unless the patient asks for them",
      "Avoid movement until lung sounds are completely normal"
    ],
    correct: [0],
    rationale: {
      whyCorrect: "The best intervention is the one that improves ventilation and secretion clearance. The other options worsen immobility complications by promoting stasis and shallow breathing.",
      whyWrong: [
        "Correct.",
        "Flat prolonged positioning can worsen respiratory complications.",
        "Fluid restriction does not best reduce secretion pooling.",
        "Avoiding movement prolongs the underlying problem."
      ],
      tip: "For lungs and immobility, think expansion plus clearance."
    }
  },
  {
    id: 56,
    section: "Immobility",
    type: "SATA",
    question: "Which consequences of prolonged immobility are most directly linked to the musculoskeletal system? Select all that apply.",
    options: [
      "Contractures",
      "Bone demineralization",
      "Muscle weakness",
      "Constipation",
      "Venous stasis",
      "Decreased joint mobility"
    ],
    correct: [0,1,2,5],
    rationale: {
      whyCorrect: "The source ties immobility to contractures, reduced joint mobility, muscle loss or weakness, and bone demineralization. The distractors come from GI and cardiovascular systems.",
      whyWrong: [
        "Correct.",
        "Correct.",
        "Correct.",
        "Constipation is GI, not musculoskeletal.",
        "Venous stasis is cardiovascular.",
        "Correct."
      ],
      tip: "Classify by body system before choosing."
    }
  },
  {
    id: 57,
    section: "Wound",
    type: "Multiple Choice",
    question: "Which wound would be expected to heal by secondary intention?",
    options: [
      "A clean surgical incision with edges well approximated by sutures",
      "A wound with tissue loss that cannot be brought together and must fill in gradually",
      "A laceration closed immediately with staples in the emergency department",
      "An incision intentionally left closed after full sterile healing"
    ],
    correct: [1],
    rationale: {
      whyCorrect: "Secondary intention healing occurs when wound edges are not approximated and tissue must fill in from the base upward. The clean approximated incision examples are primary intention.",
      whyWrong: [
        "This is primary intention.",
        "Correct.",
        "This is also primary intention because the edges are closed together.",
        "This does not describe secondary intention."
      ],
      tip: "If the edges are not together and the wound has to fill in, think secondary intention."
    }
  },
  {
    id: 58,
    section: "Wound",
    type: "Clinical Scenario",
    question: "A wound has healthy red, moist granulation tissue in the bed. Which interpretation is best?",
    options: [
      "This suggests necrosis requiring debridement",
      "This is a positive sign of healing tissue formation",
      "This proves the wound is eviscerating",
      "This means the wound must be left completely uncovered"
    ],
    correct: [1],
    rationale: {
      whyCorrect: "Granulation tissue is a healthy sign of healing. The hard part is not confusing red healthy tissue with infection or bleeding alone.",
      whyWrong: [
        "Necrosis is typically black, brown, or nonviable tissue, not healthy granulation tissue.",
        "Granulation tissue does not indicate evisceration.",
        "The presence of granulation tissue does not automatically determine that the wound should be left uncovered."
      ],
      tip: "Red can mean healing when it is moist, beefy, and healthy-looking granulation tissue."
    }
  },
  {
    id: 59,
    section: "Wound",
    type: "Priority",
    question: "Which patient has the greatest risk for delayed wound healing?",
    options: [
      "A well-nourished young adult with a small clean incision",
      "A dehydrated patient with malnutrition and wound infection",
      "A patient with a paper cut who sleeps poorly one night",
      "A patient asking questions about dressing changes"
    ],
    correct: [1],
    rationale: {
      whyCorrect: "Malnutrition, dehydration, and infection are all source-based factors that delay healing. This is a stacked-risk question, so the best answer combines several harmful factors rather than just one.",
      whyWrong: [
        "This patient has fewer major healing barriers.",
        "Correct.",
        "One poor night of sleep with a minor cut is not the greatest delay risk here.",
        "Questions do not create physiologic delay in healing."
      ],
      tip: "The best answer often bundles several true risk factors together."
    }
  },
  {
    id: 60,
    section: "Wound",
    type: "SATA",
    question: "Which findings fit an arterial ulcer more than a venous ulcer? Select all that apply.",
    options: [
      "Painful wound",
      "Pale or necrotic wound bed",
      "Lower leg edema as the main hallmark",
      "Diminished blood supply pattern",
      "Improvement mainly explained by venous return support",
      "Tissue damage related to ischemia"
    ],
    correct: [0,1,3,5],
    rationale: {
      whyCorrect: "Arterial ulcers are associated with poor blood supply, pain, ischemic tissue damage, and often a pale or necrotic wound appearance. Venous ulcers are more tied to edema and venous return problems.",
      whyWrong: [
        "Correct.",
        "Correct.",
        "This points more toward venous disease.",
        "Correct.",
        "This is more venous-focused than arterial-focused.",
        "Correct."
      ],
      tip: "Arterial = ischemia. Venous = pooling and edema."
    }
  },
  {
    id: 61,
    section: "Rest / Sleep",
    type: "Multiple Choice",
    question: "Which statement best describes REM rebound?",
    options: [
      "A complete loss of all REM sleep permanently",
      "An increase in REM sleep after earlier REM deprivation",
      "A shift from REM sleep to only stage 1 NREM sleep",
      "A normal sign of wound infection"
    ],
    correct: [1],
    rationale: {
      whyCorrect: "REM rebound refers to an increase in REM sleep after REM has been previously suppressed or deprived. The distractors exaggerate or misapply the concept.",
      whyWrong: [
        "REM rebound is not permanent loss of REM.",
        "Correct.",
        "This is not the source definition.",
        "This is unrelated to infection."
      ],
      tip: "Rebound usually means more of something after you were deprived of it."
    }
  },
  {
    id: 62,
    section: "Rest / Sleep",
    type: "Clinical Scenario",
    question: "A patient snores loudly, has repeated nighttime breathing pauses, and feels exhausted during the day. Which disorder best fits the pattern?",
    options: [
      "Sleep apnea",
      "Narcolepsy",
      "Primary insomnia only",
      "Dehiscence"
    ],
    correct: [0],
    rationale: {
      whyCorrect: "Repeated nighttime breathing pauses with daytime exhaustion strongly fit sleep apnea. The question tests pattern recognition rather than memorization of a one-word definition.",
      whyWrong: [
        "Correct.",
        "Narcolepsy centers on sudden daytime sleep attacks, not repeated nocturnal breathing pauses.",
        "Insomnia alone does not best explain the breathing pauses.",
        "Dehiscence is a wound complication, not a sleep disorder."
      ],
      tip: "Breathing pauses during sleep point to sleep apnea first."
    }
  },
  {
    id: 63,
    section: "Rest / Sleep",
    type: "Priority",
    question: "Which nursing observation would most strongly support that a hospitalized patient’s sleep problem is being worsened by the environment?",
    options: [
      "The patient wakes repeatedly after hallway noise and nighttime interruptions",
      "The patient has a history of surgery",
      "The patient asks one question about pain medication",
      "The patient has a healing wound"
    ],
    correct: [0],
    rationale: {
      whyCorrect: "Environmental noise and interruptions are source-based barriers to sleep in the hospital. The other options may matter to the overall patient experience, but they do not as directly show an environmental cause.",
      whyWrong: [
        "Correct.",
        "This does not specifically identify environment as the cause.",
        "This is not the best evidence of environmental sleep disruption.",
        "A wound alone does not prove environment is the main sleep problem."
      ],
      tip: "Look for the answer that directly ties the problem to the environment named in the stem."
    }
  },
  {
    id: 64,
    section: "Rest / Sleep",
    type: "SATA",
    question: "Which changes are commonly associated with sleep deprivation? Select all that apply.",
    options: [
      "Fatigue",
      "Irritability",
      "Decreased concentration",
      "Improved judgment",
      "Daytime sleepiness",
      "Enhanced memory performance"
    ],
    correct: [0,1,2,4],
    rationale: {
      whyCorrect: "Sleep deprivation contributes to fatigue, irritability, concentration problems, and daytime sleepiness. The distractors describe improved function, which is the opposite of what sleep deprivation causes.",
      whyWrong: [
        "Correct.",
        "Correct.",
        "Correct.",
        "Sleep deprivation worsens judgment rather than improving it.",
        "Correct.",
        "Sleep deprivation does not enhance memory performance."
      ],
      tip: "If the answer choice sounds like sharper performance, be suspicious in a sleep-deprivation question."
    }
  },
  {
    id: 65,
    section: "Mixed Integrated",
    type: "Priority",
    question: "Which patient should the nurse see first?",
    options: [
      "A patient with black eschar asking what debridement means",
      "A patient with a fentanyl patch who still has pain 2 hours after application",
      "A patient on bed rest with sudden unilateral calf swelling and warmth",
      "A patient who says the room was too bright overnight"
    ],
    correct: [2],
    rationale: {
      whyCorrect: "This question mixes wound, analgesic, immobility, and sleep issues. The unilateral warm swollen calf raises concern for venous thrombosis, which can lead to embolic complications and therefore takes priority over teaching and expected patch-onset issues.",
      whyWrong: [
        "This patient needs teaching, but not first.",
        "Pain control matters, but the patch timing may explain the pain and it is less urgent than a possible clot.",
        "Correct.",
        "Environmental sleep concerns are important but not urgent."
      ],
      tip: "Priority means asking which problem is most dangerous right now, not just most uncomfortable."
    }
  },
  {
    id: 66,
    section: "Mixed Integrated",
    type: "Clinical Scenario",
    question: "A postoperative patient with an abdominal incision is on opioids and mostly immobile. Which nursing concern is best supported if the patient becomes constipated, sleepy, and reluctant to move?",
    options: [
      "The patient has only one isolated medication side effect",
      "The patient is developing a cluster of risks that can worsen immobility and recovery",
      "The patient is showing normal healing and needs no further assessment",
      "The symptoms prove the wound is healing by primary intention"
    ],
    correct: [1],
    rationale: {
      whyCorrect: "This is a professor-style integrated item. Constipation and sedation may reflect opioid effects, while reluctance to move can worsen immobility complications and overall recovery. The best answer is the one that sees the whole cluster rather than minimizing it.",
      whyWrong: [
        "This is too narrow because more than one risk is developing.",
        "These findings should not be dismissed without further assessment.",
        "Wound-healing intention is not proven by these symptoms."
      ],
      tip: "The best answer often recognizes how one problem can make another problem worse."
    }
  },
  {
    id: 67,
    section: "Mixed Integrated",
    type: "SATA",
    question: "The nurse is preparing discharge teaching for a patient recovering from surgery. Which points appropriately combine source-based safety teaching? Select all that apply.",
    options: [
      "Report increasing wound redness, swelling, drainage, or fever",
      "Take more acetaminophen than directed if pain is still present because it is sold over the counter",
      "Call if opioids cause slowed breathing or excessive drowsiness",
      "Resume movement as instructed rather than staying in bed all day",
      "Use healthy sleep habits to support recovery when possible",
      "Ignore calf warmth and swelling if you have not had chest pain"
    ],
    correct: [0,2,3,4],
    rationale: {
      whyCorrect: "This SATA blends wound, analgesic, immobility, and sleep teaching. The correct choices are all source-supported safety points. The wrong answers encourage dangerous delay or overdose behavior.",
      whyWrong: [
        "Correct.",
        "This is unsafe because acetaminophen overdose can injure the liver.",
        "Correct.",
        "Correct.",
        "Correct.",
        "Calf warmth and swelling may indicate venous thrombosis and should not be ignored."
      ],
      tip: "Discharge teaching questions usually reward prevention, early reporting, and safe medication use."
    }
  },
  {
    id: 68,
    section: "Mixed Integrated",
    type: "Multiple Choice",
    question: "Which nursing plan best balances pain control with safety in an immobile postoperative patient?",
    options: [
      "Avoid all opioids so the patient will move more",
      "Use prescribed analgesia safely while monitoring breathing, encouraging activity as tolerated, and reassessing response",
      "Keep the patient in bed to protect the wound and medicate only after severe pain starts",
      "Give pain medication without reassessment so the patient can finally rest"
    ],
    correct: [1],
    rationale: {
      whyCorrect: "This answer balances multiple objectives: treating pain, monitoring opioid safety, encouraging mobility, and reassessing effect. The distractors each overcorrect one issue and create new risks.",
      whyWrong: [
        "Avoiding all opioids may leave pain untreated and is not the best balanced plan.",
        "Correct.",
        "Staying in bed and waiting for severe pain both worsen outcomes.",
        "Analgesics should always be followed by reassessment and monitoring."
      ],
      tip: "The best nursing plan usually balances comfort and safety instead of choosing one at the expense of the other."
    }
  },
  {
    id: 69,
    section: "Pharmacology / Med Admin",
    type: "Multiple Choice",
    question: "Which statement by a nursing student best reflects understanding of bioavailability?",
    options: [
      "It is the amount of drug that reaches systemic circulation and is available to act",
      "It means the medication has no side effects",
      "It refers only to protein binding in the plasma",
      "It is the same as the nurse’s three medication checks"
    ],
    correct: [0],
    rationale: {
      whyCorrect: "Bioavailability is the amount of administered drug that reaches the systemic circulation in active form. The other choices misuse unrelated medication concepts.",
      whyWrong: [
        "Correct.",
        "Bioavailability does not mean a medication is free of side effects.",
        "Protein binding is a different concept.",
        "Medication checks are safety steps, not a pharmacokinetic concept."
      ],
      tip: "Think availability to the body, not safety checks or side effects."
    }
  },
  {
    id: 70,
    section: "Pharmacology / Med Admin",
    type: "Clinical Scenario",
    question: "A patient says, 'This medicine used to work well, but now I need more to get the same effect.' Which concept best fits?",
    options: [
      "Tolerance",
      "Anaphylaxis",
      "First-pass effect",
      "Orthostatic hypotension"
    ],
    correct: [0],
    rationale: {
      whyCorrect: "Tolerance means the body becomes less responsive to a medication over time, so the same dose produces less effect. The distractors are real concepts but do not explain the stem.",
      whyWrong: [
        "Correct.",
        "Anaphylaxis is an acute allergic emergency, not reduced effect over time.",
        "First-pass effect is a liver metabolism concept.",
        "Orthostatic hypotension is unrelated to this pattern."
      ],
      tip: "If the same dose works less over time, think tolerance."
    }
  },
  {
    id: 71,
    section: "Analgesics",
    type: "Multiple Choice",
    question: "Which medication would the nurse identify as a nonopioid analgesic from the source material?",
    options: [
      "Morphine",
      "Acetaminophen",
      "Naloxone",
      "Fentanyl"
    ],
    correct: [1],
    rationale: {
      whyCorrect: "Acetaminophen is a nonopioid analgesic. The other options are opioid agonists or an opioid antagonist, so they belong to different categories.",
      whyWrong: [
        "Morphine is an opioid agonist.",
        "Correct.",
        "Naloxone is an opioid antagonist, not a nonopioid analgesic.",
        "Fentanyl is an opioid agonist."
      ],
      tip: "Sometimes the hard part is not overthinking a straightforward class question."
    }
  },
  {
    id: 72,
    section: "Analgesics",
    type: "Priority",
    question: "Which patient is the best candidate for immediate teaching about naloxone follow-up monitoring?",
    options: [
      "A patient who has never received any opioid",
      "A patient reversed from opioid toxicity who is now breathing better but still needs monitoring",
      "A patient asking about sleep stages",
      "A patient with a hydrogel dressing"
    ],
    correct: [1],
    rationale: {
      whyCorrect: "Even when naloxone improves breathing, monitoring must continue because the opioid effect can outlast the naloxone. This question tests whether the nurse understands the aftercare, not just the reversal itself.",
      whyWrong: [
        "There is no immediate indication for naloxone teaching here.",
        "Correct.",
        "This is unrelated content.",
        "This is unrelated content."
      ],
      tip: "After naloxone, improvement does not mean the danger is over."
    }
  },
  {
    id: 73,
    section: "Immobility",
    type: "Multiple Choice",
    question: "Which statement best explains why immobility can worsen bowel elimination?",
    options: [
      "Immobility increases peristalsis and speeds stool movement",
      "Immobility decreases GI motility, contributing to constipation",
      "Immobility causes immediate wound infection in the intestines",
      "Immobility prevents all fluid absorption"
    ],
    correct: [1],
    rationale: {
      whyCorrect: "Decreased movement contributes to decreased GI motility and constipation. The distractors either reverse the physiology or add unsupported claims.",
      whyWrong: [
        "Immobility decreases, not increases, peristalsis.",
        "Correct.",
        "This is not the source-based explanation.",
        "Immobility does not prevent all fluid absorption."
      ],
      tip: "When the body moves less, the bowel often moves less too."
    }
  },
  {
    id: 74,
    section: "Immobility",
    type: "Priority",
    question: "Which immobile patient requires the most immediate intervention?",
    options: [
      "A patient with decreased joint range of motion over several days",
      "A patient with sudden shortness of breath and chest pain",
      "A patient who has not had a bowel movement in 2 days",
      "A patient asking why body mechanics matter"
    ],
    correct: [1],
    rationale: {
      whyCorrect: "Sudden shortness of breath and chest pain raise concern for pulmonary embolism, which is a life-threatening emergency. The other issues matter but are less immediately dangerous.",
      whyWrong: [
        "This requires care, but it is not the most urgent problem.",
        "Correct.",
        "Constipation matters but is not more urgent than a possible embolus.",
        "Teaching can wait."
      ],
      tip: "Acute cardiopulmonary symptoms beat chronic complications in priority ranking."
    }
  },
  {
    id: 75,
    section: "Wound",
    type: "Multiple Choice",
    question: "Which statement best explains tertiary intention wound healing?",
    options: [
      "The wound is closed immediately with staples or sutures",
      "The wound is left open at first and later closed after contamination or swelling is controlled",
      "The wound heals only under a hydrogel dressing",
      "The wound edges are always approximated from the beginning"
    ],
    correct: [1],
    rationale: {
      whyCorrect: "Tertiary intention involves delayed closure after the wound is initially left open, often to manage contamination or swelling. The distractors either describe primary intention or make unsupported claims.",
      whyWrong: [
        "This is primary intention.",
        "Correct.",
        "Dressings do not define tertiary intention by themselves.",
        "This does not match delayed closure."
      ],
      tip: "Tertiary = delayed closure."
    }
  },
  {
    id: 76,
    section: "Wound",
    type: "Clinical Scenario",
    question: "A patient with a pressure injury has prolonged moisture exposure and poor nutrition. Which judgment is best?",
    options: [
      "These factors can delay healing and worsen tissue damage risk",
      "These findings only affect sleep and not skin integrity",
      "Moisture exposure always improves wound healing",
      "Nutrition has no meaningful role once a wound is present"
    ],
    correct: [0],
    rationale: {
      whyCorrect: "Moisture and poor nutrition are source-based factors that increase skin breakdown risk and slow healing. The distractors ignore major wound-healing principles.",
      whyWrong: [
        "Correct.",
        "These findings directly affect skin integrity and healing.",
        "Excess moisture can damage skin rather than helping it.",
        "Nutrition remains important throughout healing."
      ],
      tip: "If it weakens tissue or weakens healing, it matters."
    }
  },
  {
    id: 77,
    section: "Rest / Sleep",
    type: "Multiple Choice",
    question: "Which statement about stage 1 NREM sleep is most accurate?",
    options: [
      "It is a light transition stage from wakefulness into sleep",
      "It is the deepest restorative stage with the hardest arousal",
      "It is the stage of vivid dreaming and muscle atonia",
      "It is identical to REM sleep"
    ],
    correct: [0],
    rationale: {
      whyCorrect: "Stage 1 NREM is a light transitional stage. The distractors describe deeper NREM or REM features instead.",
      whyWrong: [
        "Correct.",
        "This describes deeper sleep rather than stage 1.",
        "This describes REM.",
        "Stage 1 NREM is not the same as REM."
      ],
      tip: "Stage 1 = light entry into sleep."
    }
  },
  {
    id: 78,
    section: "Rest / Sleep",
    type: "Clinical Scenario",
    question: "An older adult says, 'I wake up more often now and sleep more lightly than I used to.' Which response is best?",
    options: [
      "Older adults commonly experience changes in sleep pattern, but sleep problems should still be assessed rather than dismissed",
      "That means you definitely have narcolepsy",
      "That always means your wound is infected",
      "Sleep changes in older adults are never clinically relevant"
    ],
    correct: [0],
    rationale: {
      whyCorrect: "The source supports that sleep patterns can change with aging, but assessment still matters. The best answer validates the report without dismissing potential problems.",
      whyWrong: [
        "Correct.",
        "Narcolepsy is not the best conclusion here.",
        "Wound infection is unrelated to the statement.",
        "Sleep changes remain clinically relevant."
      ],
      tip: "Good nursing answers usually validate and assess rather than dismiss or overdiagnose."
    }
  },
  {
    id: 79,
    section: "Mixed Integrated",
    type: "Priority",
    question: "Which issue should the nurse address first during a busy shift?",
    options: [
      "A patient asks whether REM stands for rapid eye movement",
      "A patient with a postoperative wound now has bowel loops visible through the incision",
      "A patient asks whether acetaminophen and NSAIDs are both nonopioids",
      "A patient says the room was too warm last night"
    ],
    correct: [1],
    rationale: {
      whyCorrect: "Visible bowel loops indicate evisceration, which is a surgical emergency. The other concerns involve teaching or comfort, but evisceration is immediately life- and tissue-threatening.",
      whyWrong: [
        "This is a teaching question, not the priority.",
        "Correct.",
        "This is also teaching, not the priority.",
        "Comfort matters, but not before an emergency."
      ],
      tip: "Emergency tissue exposure beats all routine teaching concerns."
    }
  },
  {
    id: 80,
    section: "Mixed Integrated",
    type: "Clinical Scenario",
    question: "A patient recovering from surgery has moderate pain, poor sleep, reluctance to move, and an incision that is still being monitored for infection. Which nursing approach is best?",
    options: [
      "Treat each problem separately and ignore how they influence one another",
      "Use an integrated plan that addresses pain control, mobility, wound assessment, and sleep-promoting measures together",
      "Prioritize only sleep because rest solves all the other problems",
      "Keep the patient on strict bed rest until all discomfort is gone"
    ],
    correct: [1],
    rationale: {
      whyCorrect: "This final item mirrors your professor’s combined-objective style. Pain, mobility, wound healing, and sleep all affect one another in recovery. The best plan is integrated rather than narrow.",
      whyWrong: [
        "This misses the interaction among the patient’s current risks and needs.",
        "Sleep is important, but it is not the only needed focus.",
        "Strict bed rest worsens immobility-related risk."
      ],
      tip: "When the stem gives several linked recovery issues, the best answer is often the plan that connects them."
    }
  }
];

function isCorrectSelection(selected, correct) {
  if (selected.length !== correct.length) return false;
  const a = [...selected].sort((x, y) => x - y);
  const b = [...correct].sort((x, y) => x - y);
  return a.every((v, i) => v === b[i]);
}

function isCaseQuestion(type) {
  return type.toLowerCase().includes("case study");
}

export default function Test2InteractiveNursingMockExam() {
  const [current, setCurrent] = useState(0);
  const [answers, setAnswers] = useState({});
  const [submitted, setSubmitted] = useState({});
  const [showOnlyMissed, setShowOnlyMissed] = useState(false);

  const filteredIndexes = useMemo(() => {
    const all = questions.map((_, i) => i);
    if (!showOnlyMissed) return all;
    return all.filter((i) => submitted[i] && !isCorrectSelection(answers[i] || [], questions[i].correct));
  }, [answers, submitted, showOnlyMissed]);

  const effectiveIndex = filteredIndexes.includes(current)
    ? current
    : filteredIndexes[0] ?? 0;

  const q = questions[effectiveIndex];
  const selected = answers[effectiveIndex] || [];
  const isSubmitted = !!submitted[effectiveIndex];
  const correctNow = isSubmitted && isCorrectSelection(selected, q.correct);

  const score = questions.reduce((acc, question, i) => {
    if (submitted[i] && isCorrectSelection(answers[i] || [], question.correct)) return acc + 1;
    return acc;
  }, 0);

  const answeredCount = Object.keys(submitted).length;

  const toggleOption = (idx) => {
    if (isSubmitted) return;
    const isSATA = q.type === "SATA";
    if (isSATA) {
      setAnswers((prev) => {
        const cur = prev[effectiveIndex] || [];
        return {
          ...prev,
          [effectiveIndex]: cur.includes(idx) ? cur.filter((x) => x !== idx) : [...cur, idx]
        };
      });
    } else {
      setAnswers((prev) => ({ ...prev, [effectiveIndex]: [idx] }));
    }
  };

  const submitAnswer = () => {
    if (!selected.length) return;
    setSubmitted((prev) => ({ ...prev, [effectiveIndex]: true }));
  };

  const resetCurrent = () => {
    setSubmitted((prev) => {
      const next = { ...prev };
      delete next[effectiveIndex];
      return next;
    });
    setAnswers((prev) => ({ ...prev, [effectiveIndex]: [] }));
  };

  const goNext = () => {
    const pos = filteredIndexes.indexOf(effectiveIndex);
    const next = filteredIndexes[pos + 1];
    if (next !== undefined) setCurrent(next);
  };

  const goPrev = () => {
    const pos = filteredIndexes.indexOf(effectiveIndex);
    const prev = filteredIndexes[pos - 1];
    if (prev !== undefined) setCurrent(prev);
  };

  return (
    <div className="min-h-screen bg-neutral-50 p-4 md:p-8">
      <div className="mx-auto max-w-5xl space-y-6">
        <div className="rounded-3xl bg-white p-6 shadow-sm border">
          <div className="flex flex-col gap-4 md:flex-row md:items-end md:justify-between">
            <div>
              <h1 className="text-3xl font-semibold tracking-tight">Test 2 Interactive Nursing Mock Exam</h1>
              <p className="mt-2 text-sm text-neutral-600">
                Built from the uploaded pharmacology, analgesics, immobility, wound, and rest/sleep sources only.
              </p>
            </div>
            <div className="grid grid-cols-2 gap-3 md:grid-cols-4">
              <div className="rounded-2xl border p-3">
                <div className="text-xs text-neutral-500">Questions</div>
                <div className="text-xl font-semibold">{questions.length}</div>
              </div>
              <div className="rounded-2xl border p-3">
                <div className="text-xs text-neutral-500">Answered</div>
                <div className="text-xl font-semibold">{answeredCount}</div>
              </div>
              <div className="rounded-2xl border p-3">
                <div className="text-xs text-neutral-500">Correct</div>
                <div className="text-xl font-semibold">{score}</div>
              </div>
              <div className="rounded-2xl border p-3">
                <div className="text-xs text-neutral-500">Mode</div>
                <button
                  onClick={() => {
                    setShowOnlyMissed((v) => !v);
                    setCurrent(0);
                  }}
                  className="mt-1 rounded-xl border px-3 py-1 text-sm hover:bg-neutral-100"
                >
                  {showOnlyMissed ? "Missed Only" : "All Questions"}
                </button>
              </div>
            </div>
          </div>
        </div>

        <div className="rounded-3xl bg-white p-6 shadow-sm border">
          <div className="flex flex-wrap items-center gap-2 text-xs text-neutral-600">
            <span className="rounded-full bg-neutral-100 px-3 py-1">{q.section}</span>
            <span className="rounded-full bg-neutral-100 px-3 py-1">{q.type}</span>
            <span className="rounded-full bg-neutral-100 px-3 py-1">Question {effectiveIndex + 1} of {questions.length}</span>
          </div>

          <h2 className="mt-4 text-xl md:text-2xl font-semibold leading-tight">{q.question}</h2>

          <div className="mt-6 space-y-3">
            {q.options.map((opt, idx) => {
              const chosen = selected.includes(idx);
              const revealCorrect = isSubmitted && q.correct.includes(idx);
              const revealWrong = isSubmitted && chosen && !q.correct.includes(idx);
              return (
                <button
                  key={idx}
                  onClick={() => toggleOption(idx)}
                  className={`w-full rounded-2xl border p-4 text-left transition ${
                    revealCorrect
                      ? "border-green-500 bg-green-50"
                      : revealWrong
                      ? "border-red-500 bg-red-50"
                      : chosen
                      ? "border-neutral-900 bg-neutral-100"
                      : "hover:bg-neutral-50"
                  }`}
                >
                  <div className="flex gap-3">
                    <div className="font-semibold">{String.fromCharCode(65 + idx)}.</div>
                    <div>{opt}</div>
                  </div>
                </button>
              );
            })}
          </div>

          <div className="mt-6 flex flex-wrap gap-3">
            <button onClick={goPrev} className="rounded-2xl border px-4 py-2 hover:bg-neutral-100">Previous</button>
            <button onClick={submitAnswer} className="rounded-2xl bg-neutral-900 px-4 py-2 text-white disabled:opacity-40" disabled={!selected.length || isSubmitted}>Submit</button>
            <button onClick={resetCurrent} className="rounded-2xl border px-4 py-2 hover:bg-neutral-100">Reset</button>
            <button onClick={goNext} className="rounded-2xl border px-4 py-2 hover:bg-neutral-100">Next</button>
          </div>
        </div>

        {isSubmitted && (
          <div className={`rounded-3xl border p-6 shadow-sm ${correctNow ? "bg-green-50 border-green-300" : "bg-red-50 border-red-300"}`}>
            <h3 className="text-xl font-semibold">{correctNow ? "Correct" : "Review"}</h3>
            <p className="mt-3"><span className="font-semibold">Correct Answer:</span> {q.correct.map((i) => String.fromCharCode(65 + i)).join(", ")}</p>
            <div className="mt-4 space-y-4 text-sm leading-6 text-neutral-800">
              <div>
                <div className="font-semibold">Why the correct answer is correct</div>
                <p>{q.rationale.whyCorrect}</p>
              </div>
              <div>
                <div className="font-semibold">Why the other options are wrong</div>
                <ul className="list-disc pl-5 space-y-1">
                  {q.rationale.whyWrong.map((text, idx) => (
                    <li key={idx}><span className="font-medium">{String.fromCharCode(65 + idx)}.</span> {text}</li>
                  ))}
                </ul>
              </div>
              <div>
                <div className="font-semibold">Test-taking tip</div>
                <p>{q.rationale.tip}</p>
              </div>
            </div>
          </div>
        )}

        <div className="rounded-3xl bg-white p-6 shadow-sm border">
          <h3 className="text-lg font-semibold">Question Navigator</h3>
          <div className="mt-4 flex flex-wrap gap-2">
            {questions.map((item, i) => {
              const done = submitted[i];
              const gotRight = done && isCorrectSelection(answers[i] || [], item.correct);
              const gotWrong = done && !gotRight;
              return (
                <button
                  key={item.id}
                  onClick={() => setCurrent(i)}
                  className={`h-10 w-10 rounded-xl border text-sm font-medium ${
                    i === effectiveIndex
                      ? "border-neutral-900 bg-neutral-900 text-white"
                      : gotRight
                      ? "border-green-500 bg-green-50 text-green-700"
                      : gotWrong
                      ? "border-red-500 bg-red-50 text-red-700"
                      : "hover:bg-neutral-50"
                  }`}
                >
                  {i + 1}
                </button>
              );
            })}
          </div>
        </div>
      </div>
    </div>
  );
}
