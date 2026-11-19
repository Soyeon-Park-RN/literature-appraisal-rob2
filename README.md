# RoB 2 Quality Appraisal — Claude Skill

RCT 논문의 비뚤림 위험을 평가하는 RoB 2를 Claude와 함께 연습하는 스킬입니다. 논문 PDF를 올리면 다섯 개 도메인의 질문이 대화창에 하나씩 나타납니다. 질문마다 논문의 어디를 보면 되는지, 어떤 점을 헷갈리기 쉬운지 안내가 붙어 있으니 그걸 참고해 먼저 답을 고르세요. 그다음 Claude의 답과 비교합니다. 
답이 다르면 왜 다른지(이 질문이 무엇을 가려내려는지, 논문의 어느 문장이 근거인지, 왜 그 답인지)자세히 설명해 줍니다. 
최종 결정은 언제나 여러분이 합니다. 도메인 판정과 전체 판정은 여러분의 답을 RoB 2 규칙에 넣어 자동으로 나오고, 어떤 답이 판정을 결정했는지도 보여 줍니다. 
결과는 신호등 표가 들어 있는 엑셀로 받습니다.

![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)
![Claude Skill](https://img.shields.io/badge/Claude-Skill-orange.svg)
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.XXXXXXXX.svg)](https://doi.org/10.5281/zenodo.XXXXXXXX)

## 이 스킬로 할 수 있는 것

- **논문 개요 확인** — 대상자, 실험군과 대조군, 주 종속변수, 통계 기법, 사전 등록 여부를 Claude가 먼저 정리해 보여 줍니다. 틀린 곳이 있으면 고쳐 주면 됩니다.
- **도메인마다 안내 받기** — 각 도메인이 왜 중요한지, 질문마다 논문의 어디를 보면 되는지, 어떤 함정에 빠지기 쉬운지를 질문과 함께 보여 줍니다.
- **먼저 답하고 비교하기** — 질문에 여러분이 먼저 응답과 근거(페이지)를 적습니다. 그 뒤에 Claude의 응답을 봅니다. 앞 질문의 답이 정해져야 다음 질문이 열립니다.
- **다른 답만 자세히 배우기** — 답이 같으면 한 줄로 넘어갑니다. 다르면 개념 → 논문의 근거 문장 → 왜 그 답인지 → 헷갈리기 쉬운 이유 순으로 설명을 읽고, 여러분이 최종 답을 정합니다.
- **판정이 나오는 과정 보기** — 도메인의 답이 모두 정해지면 RoB 2 규칙에 따라 판정이 나옵니다. 어떤 답 때문에 그 판정이 됐는지, 무엇이 달랐으면 판정이 바뀌었을지 함께 보여 줍니다. 이의가 있으면 이유를 적고 바꿀 수 있습니다.
- **효과 유형 정하기** — 배정 효과(ITT)와 순응 효과(PP) 중 어느 것을 볼지 첫 논문에서 한 번 고릅니다. 간호학 중재 연구는 대부분 배정 효과입니다.
- **엑셀로 받기** — 여러분의 답, Claude의 답, 최종 답, 왜 달랐는지, 근거 위치가 모두 남습니다. 공식 RoB 2 도구와 같은 모양의 신호등 표와 도메인별 분포 차트도 들어 있습니다. 논문 1편이 끝날 때마다 자동으로 저장되고 다음 논문이 이어서 쌓입니다.
- **중간에 끊겨도 이어가기** — 저장된 엑셀을 올리면 멈춘 도메인부터 다시 시작합니다.

## 설치 및 사용 방법

1. literature-appraisal-rob2.skill 다운로드
2. Claude.ai → 대화창 "+" 클릭 → 스킬 클릭 → 스킬 관리 클릭 → "추가" 클릭 → "스킬 업로드" 클릭 → 다운로드 받은 스킬 업로드
3. 새 대화에 RCT 논문 PDF 1편을 첨부하고 "+" 클릭 후 스킬 선택 후 Enter
4. Claude가 정리한 논문 개요를 읽고, 다르면 고쳐 줍니다
5. 효과 유형을 고릅니다 — 특별한 이유가 없으면 배정 효과(ITT)
6. 도메인마다 나타나는 질문에서 "어디를 보세요"를 참고해 논문을 찾아 읽고, 답과 근거(페이지)를 적은 뒤 "계속"을 누릅니다
7. Claude의 답과 다른 질문은 설명을 읽고 최종 답을 정합니다
8. 도메인 판정과 전체 판정을 확인합니다 — 이의가 있으면 이유를 적어 바꿀 수 있습니다
9. 논문 1편이 끝나면 엑셀이 자동으로 옵니다 — 다음 논문을 첨부해 이어가고, 다 끝나면 "끝"이라고 입력합니다

대화가 끊겼으면 새 대화에 최신 엑셀과 PDF를 첨부하고 "이어서 해주세요."라고 하면 됩니다. 엑셀의 `_기록` 시트는 이어가기에 쓰이니 편집하거나 지우지 마세요.

## 사용하기 전에 알아 둘 것

- **먼저 답하는 것이 핵심입니다.** Claude의 답을 보고 따라 적으면 배우는 게 없습니다. "어디를 보세요"를 따라 논문을 직접 찾아 읽고 답하세요. 틀려도 괜찮습니다 — 틀린 문항에서 가장 많이 배웁니다.
- **"모르겠다"는 답이 아닙니다.** 판단이 안 서면 가장 가깝다고 생각하는 쪽을 고르고 근거란에 "확신 없음"이라고 적으세요. Claude가 비교하면서 설명해 줍니다. 정보 없음(NI)은 논문을 다 찾아봤는데 정말 기술이 없을 때만 고릅니다.
- **RCT만 됩니다.** 개인 단위로 무작위 배정한 평행군 RCT가 아니면(군집 무작위, 교차 설계, 비무작위 연구) 평가하지 않습니다. 논문을 올리면 Claude가 먼저 확인해 줍니다.
- **연구당 한 번 평가합니다.** RoB 2는 원래 결과(outcome)마다 평가하는 도구지만, 여기서는 논문의 주 종속변수를 기준으로 한 번만 합니다.
- **판정은 규칙대로입니다.** 원 도구에서는 Some concerns가 여러 도메인에 겹치면 평가자가 High로 올릴 수 있지만, 이 학습 버전에서는 규칙 그대로 둡니다.
- **질문 문구는 요약본입니다.** 원 도구의 질문을 학부생이 읽기 쉽게 풀어 쓴 것이니, 실제 과제나 논문에 쓸 때는 원본(riskofbias.info)을 함께 보세요.
- **Claude와 답이 같다고 정답은 아닙니다.** 일치율은 정확도의 지표가 아닙니다. 과제·논문에는 생성형 AI의 도움을 받았다는 사실과 RoB 2 버전(2019-08-22)을 적으세요.

## 인용 및 출처

이 도구를 사용한 과제나 논문에는 RoB 2 원 논문을 인용해 주세요:

Sterne JAC, Savović J, Page MJ, Elbers RG, Blencowe NS, Boutron I, et al. RoB 2: a revised tool for assessing risk of bias in randomised trials. BMJ 2019;366:l4898. doi: 10.1136/bmj.l4898

이 스킬 자체를 인용할 때는 아래 형식을 사용해 주세요(필요시):

Park S., Choe J., Woo K. (2026). literature-appraisal-rob2: A Claude skill for learning RoB 2 risk-of-bias assessment of randomized trials (Version 1.0) [Computer software]. ANDA Lab, Seoul National University College of Nursing. https://doi.org/10.5281/zenodo.XXXXXXXX

RoB 2 도구(가이던스 문서·cribsheet, 2019년 8월 22일 버전)는 RoB 2 Development Group이 Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 (CC BY-NC-ND 4.0) 라이선스로 배포합니다. 이 스킬은 해당 도구의 신호질문과 알고리즘을 요약·의역해 학습용으로 재구성한 독립 구현물이며, Cochrane 및 RoB 2 Development Group의 공식 승인을 받은 것은 아닙니다. 원본: https://www.riskofbias.info

## 라이선스

소스 코드 및 스킬 문서: MIT License © 2026 Soyeon Park
RoB 2 도구 내용(`references/rob2_tool.md`, `references/rob2_teaching.md`에 요약된 신호질문·알고리즘): © RoB 2 Development Group, CC BY-NC-ND 4.0 — 비영리 목적에 한하며 원 출처를 표기해야 합니다.

## 제작자

박소연 (Soyeon Park) — 서울대학교 간호대학 박사과정 · 스킬 설계·개발

rnsy1029@snu.ac.kr

최정인 (Jeongin Choe) — 수원과학대학교 조교수 · 검토·개선

nncj91@snu.ac.kr

## 지도교수

우경미 (Kyungmi Woo) — 서울대학교 간호대학 부교수

ANDA Lab: https://andalab.snu.ac.kr/

## 감사의 말

이 도구는 AI 도구(Claude, Anthropic)를 활용하여 개발되었습니다. 모든 설계 결정, 요구사항 정의 및 검증은 제작자가 수행했습니다.

---

# RoB 2 Quality Appraisal — Claude Skill (English)

A Claude skill for practising RoB 2, the Cochrane risk-of-bias tool for randomized trials. Upload an RCT paper and the questions for the five domains appear one at a time in the chat. Each question comes with a note on where to look in the paper and what is easy to get wrong — use it to choose your answer first. Then compare with Claude's answer. Where they differ, you get a full explanation: what the question is really asking, which sentence in the paper is the evidence, and why that answer follows. The final decision is always yours. Domain and overall judgements are produced automatically by putting your answers through the RoB 2 rules, and you are shown which answer determined each judgement. Results come back as an Excel file with a traffic-light table.

![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)
![Claude Skill](https://img.shields.io/badge/Claude-Skill-orange.svg)
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.XXXXXXXX.svg)](https://doi.org/10.5281/zenodo.XXXXXXXX)

## What you can do with this skill

- **Check the study summary** — Claude first summarizes the participants, intervention and comparator, primary dependent variable, statistical methods and trial registration. Correct anything that is wrong.
- **Get guidance for each domain** — Each question comes with why the domain matters, where in the paper to look, and the common traps.
- **Answer first, then compare** — You enter your response and evidence (page) before seeing Claude's response. The next question opens only after yours is settled.
- **Learn from the ones you got different** — If you agree, it moves on in one line. If you differ, you read a four-step explanation (concept → the sentence in the paper → why that answer → why it is easy to confuse) and make the final decision.
- **See how the judgement is reached** — Once all answers in a domain are settled, the judgement follows the RoB 2 rules. You are shown which answer decided it and what would have changed it. You can change a judgement by giving a reason.
- **Choose the effect of interest** — Pick the effect of assignment (ITT) or the effect of adherence (PP) once, with the first paper. Most nursing intervention reviews use assignment.
- **Get it in Excel** — Your answers, Claude's answers, the final answers, why they differed and where the evidence is are all kept. The file also has a traffic-light table in the style of the official RoB 2 tool and a per-domain distribution chart. It is saved automatically after each paper and the next paper is added to it.
- **Pick up where you left off** — Upload the saved Excel file and you continue from the domain where you stopped.

## Installation & Usage

1. Download literature-appraisal-rob2.skill
2. In Claude.ai, click "+" in the chat box → Skills → Manage skills → Add → Upload skill → upload the downloaded file
3. In a new chat, attach one RCT paper (PDF), click "+", select the skill and press Enter
4. Read Claude's study summary and correct it if needed
5. Choose the effect of interest — assignment (ITT) unless you have a specific reason
6. For each domain, use "where to look" to find and read the relevant part of the paper, enter your answer and page number, and click Continue
7. Where Claude's answer differs, read the explanation and decide your final answer
8. Check the domain and overall judgements — you can change one by giving a reason
9. After each paper the Excel file arrives automatically — attach the next paper to continue, and type "끝" (done) when you are finished

If the chat was interrupted, attach the latest Excel file and the PDF in a new chat and ask to continue. The `_기록` sheet in the Excel file is used for resuming, so do not edit or delete it.

## Before you start

- **Answering first is the point.** If you look at Claude's answer and copy it, you learn nothing. Follow "where to look", read the paper yourself and answer. It is fine to be wrong — you learn most from the items you got different.
- **"I don't know" is not an answer.** If you cannot decide, choose the closest option and write "not sure" in the evidence box. Claude will explain while comparing. Choose No information (NI) only when you have searched the paper and there really is nothing.
- **RCTs only.** Papers that are not individually randomized parallel-group RCTs (cluster-randomized, crossover, non-randomized) are not appraised. Claude checks this when you upload.
- **One appraisal per study.** RoB 2 is designed to be applied per outcome, but here it is done once, using the paper's primary dependent variable.
- **Judgements follow the rules.** In the original tool a reviewer may upgrade several Some concerns to High; this learning version keeps the rule as is.
- **The questions are paraphrased.** They are the original tool's questions rewritten for undergraduates. For assignments and manuscripts, consult the original (riskofbias.info) as well.
- **Agreeing with Claude does not mean you are right.** The agreement rate is not a measure of accuracy. State that you used generative AI assistance and the RoB 2 version (22 August 2019) in assignments and manuscripts.

## Citation & Attribution

If you use this tool in an assignment or manuscript, please cite the original RoB 2 publication:

Sterne JAC, Savović J, Page MJ, Elbers RG, Blencowe NS, Boutron I, et al. RoB 2: a revised tool for assessing risk of bias in randomised trials. BMJ 2019;366:l4898. doi: 10.1136/bmj.l4898

If you wish to cite this skill itself, please use the following format:

Park S., Choe J., Woo K. (2026). literature-appraisal-rob2: A Claude skill for learning RoB 2 risk-of-bias assessment of randomized trials (Version 1.0) [Computer software]. ANDA Lab, Seoul National University College of Nursing. https://doi.org/10.5281/zenodo.XXXXXXXX

The RoB 2 tool (guidance document and cribsheet, version 22 August 2019) is distributed by the RoB 2 Development Group under the Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 (CC BY-NC-ND 4.0) license. This skill is an independent implementation that summarizes and paraphrases the tool's signalling questions and algorithms for educational use, and is not officially endorsed by Cochrane or the RoB 2 Development Group. Original: https://www.riskofbias.info

## License

Source code and skill documentation: MIT License © 2026 Soyeon Park
RoB 2 tool content (signalling questions and algorithms summarized in `references/rob2_tool.md` and `references/rob2_teaching.md`): © RoB 2 Development Group, CC BY-NC-ND 4.0 — non-commercial use only, with attribution to the original source.

## Author

Soyeon Park (박소연) — Doctoral Student, College of Nursing, Seoul National University · Design and development

rnsy1029@snu.ac.kr

Jeongin Choe (최정인) — Assistant Professor, Suwon Science College · Review and improvement

nncj91@snu.ac.kr

## Advisor

Kyungmi Woo (우경미) — Associate Professor, College of Nursing, Seoul National University

ANDA Lab: https://andalab.snu.ac.kr/

## Acknowledgements

Developed with the assistance of AI tools (Claude, Anthropic). All design decisions, requirements, and validation were performed by the author.
