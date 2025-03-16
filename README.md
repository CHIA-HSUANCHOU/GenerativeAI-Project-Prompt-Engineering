# GenerativeAI-Project-Prompt-Engineering

---
Author: CHOU CHIA-HSUAN

Date: 2025-03-18

Course: Generative AI

---

## 1. Overview  

This repository presents an analysis of different **prompt engineering strategies** applied to multiple-choice question answering using **Gemini-2.0-flash**.  

The dataset consists of **10 subjects**, including:  
- Biology  
- Computer Science  
- European History  
- US History  
- World History  
- Geography  
- Government & Politics  
- Microeconomics  
- Macroeconomics  
- Psychology  

## 2. Prompting Strategies and Accuracy

| Subject               | ICL Accuracy | ZOT Accuracy | Strategy Used             |
|-----------------------|-------------|-------------|---------------------------|
| Biology              | 0.947368     | 0.966102    | Zero Shot Chain of Thought |
| Computer Science     | 0.933333     | 1.000000    | Zero Shot Chain of Thought |
| European History     | 0.791667     | 0.846154    | Zero Shot Chain of Thought |
| Geography           | 0.916667     | 0.894737    | In-Context Learning       |
| Government & Politics | 1.000000     | 1.000000    | In-Context Learning       |
| Macroeconomics       | 0.911392     | 0.901235    | In-Context Learning       |
| Microeconomics       | 0.945946     | 0.948718    | Zero Shot Chain of Thought |
| Psychology          | 0.905172     | 0.957983    | Zero Shot Chain of Thought |
| US History          | 0.871795     | 0.902439    | Zero Shot Chain of Thought |
| World History       | 0.903846     | 0.907407    | Zero Shot Chain of Thought |

Based on the nature of the questions and accuracy results, we assigned the most effective prompting strategy to each subject:

- **Few-Shot In-Context Learning (ICL)** was used for:
  - Geography  
  - Government & Politics  
  - Macroeconomics  

- **Zero-Shot Chain of Thought (ZOT)** was used for:
  - Biology  
  - Computer Science  
  - European History  
  - Microeconomics  
  - Psychology  
  - US History  
  - World History  

## 3. Prompts for Different Tasks

I. Choosing Ⅰ、Ⅱ、Ⅲ、Ⅳ correct statements(119、137、145、222、250、272、429、487)： 
**Role play prompts templates => One Shot in context learning for choosingⅠ、Ⅱ、Ⅲ、Ⅳ=>Questions=> Let’s think step by step. And choose one of the following: 'A', 'B', 'C', or 'D'.**

**[Role play prompt]**
"This is a multiple-choice test on microeconomics." 
"You are a professor who has been researching microeconomics. for 20 years. " 
"Analyze the question carefully before selecting the most accurate answer. " 
"Answer them correctly and choose the most logical answer. " 
"Your response MUST be only one of the following: 'A', 'B', 'C', or 'D'. " 
"Do not provide explanations or reasoning, just the letter of the correct answer." 
"If you are uncertain, use your expertise to choose the most reasonable answer." 

**[One Shot in context learning for choosingⅠ、Ⅱ、Ⅲ、Ⅳ]**
Question: Classical economists generally believe that 
I. Say's law does not hold 
II. input and output prices will stay in line with each other 
III. wages fluctuate quickly 
IV. the government should not worry about maintaining aggregate demand at an adequate level 
A) II and IV only 
B) I III and IV only 
C) I and IV only 
D) II and III only 
Correct Answer: B 

**[New Question]**
Now, answer the following question: 
Question: In order for a firm to successfully carry out price discrimination, which 
of the following conditions must hold? I. The firm cannot face a downward sloping 
demand curve. II. The firm must have market power. III. Buyers with differing 
demand elasticities must be separable. IV. The firm must have motives beyond profit 
maximization. V. The firm must be able to prevent the re-sale of its products. 
A) I, III, and V only 
B) III and IV only 
C) I and IV only 
D) II, III, and V only 

**Let's think step by step.** And choose one of the following: 'A', 'B', 'C', or 'D'.

II. geography、government and politics、macroeconomics(and NOT I)： 
**Role play prompts =>Few shots In context learning for choosing=> Question**

**[Role play prompt]**
This is a multiple-choice test on macroeconomics. 
You are a professor who has been researching macroeconomics for 20 years.  
Analyze the question carefully before selecting the most accurate answer.  
Answer them correctly and choose the most logical answer.  
Your response MUST be only one of the following: 'A', 'B', 'C', or 'D'.  
Do not provide explanations or reasoning, just the letter of the correct answer. 
If you are uncertain, use your expertise to choose the most reasonable answer. 

**[Few shots In context learning for choosing]**
Question: Tariffs and quotas 
A) result in lower domestic prices. 
B) sometimes raise and sometimes lower the amount of the product 
sold domestically. 
C) lower the amount of the product sold domestically. 
D) raise the amount of the product sold domestically. 
Correct Answer: C 
Question: Which group of people will suffer the most from a rising price level? 
A) debtors with fixed interest rates 
B) people with fixed money incomes 
C) investors in gems coins and stamps 
D) property owners 
Correct Answer: B 

**[New Question]**
Now, answer the following question: 
Question: According to Classical economic analysis in the long run an increase in 
the money supply results in 
A) a proportional increase in the quantity of output. 
B) stagflation. 
C) an increase in the real rate of interest. 
D) a proportional increase in the price level.


III. european history、us history、world history、Psychology、microeconomics、computer science、Biology (and NOT Ｉ)： 
**Role play prompts templates =>Question=> Zero shot chain of thought(Let’s think step by step. And choose one of the following: 'A', 'B', 'C', or 'D'.)**

**[Role play prompt]**
This is a multiple-choice test on psychology. 
You are a professor who has been researching psychology for 20 years. 
Analyze the question carefully before selecting the most accurate answer. 
Answer them correctly and choose the most logical answer.  
Your response MUST be only one of the following: 'A', 'B', 'C', or 'D'. 
Do not provide explanations or reasoning, just the letter of the correct answer. 
If you are uncertain, use your expertise to choose the most reasonable answer. 

**[New Question]**
Now, answer the following question: 
Question: Which of the following has been linked to a deficit of dopamine? 
A) major depressive disorder 
B) autism 
C) Parkinson's disease 
D) Alzheimer's disease 

**[Zero shot chain of thought]**
Let's think step by step. And choose one of the following: 'A', 'B', 'C', or 'D'.




