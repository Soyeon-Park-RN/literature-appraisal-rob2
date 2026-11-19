# RoB 2 Quality Appraisal — Claude Skill

무작위대조시험(RCT)의 비뚤림 위험 평가 도구 RoB 2를 Claude 안에서 학습하는 학부생용 스킬입니다. 논문 PDF를 올리면 5개 도메인의 신호질문이 대화창에 입력 폼으로 나타나고, 학생이 먼저 응답한 뒤 AI 응답과 비교합니다. 답이 다른 문항은 개념 → 논문의 근거 문장 → 응답 이유 → 흔히 헷갈리는 지점 순으로 설명하고, 도메인·전체 판정은 RoB 2 알고리즘으로 산출해 그 경로를 보여 줍니다. 결과는 신호등 시트가 포함된 엑셀로 저장됩니다.

![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)
![Claude Skill](https://img.shields.io/badge/Claude-Skill-orange.svg)
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.XXXXXXXX.svg)](https://doi.org/10.5281/zenodo.XXXXXXXX)

## 주요 기능

- **논문 개요 자동 정리** — 대상자, 실험군/대조군, 주 종속변수, 통계 기법, 사전 등록 여부를 AI가 읽어 보여 주고 학생이 확인
- **도메인별 안내** — 5개 도메인마다 왜 중요한지, 각 신호질문에서 논문의 어디를 보면 되는지, 흔한 함정이 무엇인지를 입력 폼과 함께 제시
- **학생 선행 응답** — 신호질문에 학생이 먼저 응답과 근거(페이지)를 적은 뒤 AI 응답과 비교. 앞 문항이 확정되어야 뒤 문항이 열림
- **불일치 해설** — 답이 다른 문항만 개념·근거 문장·응답 이유·헷갈리는 이유 4단계로 설명. 최종 판단은 학생이 결정
- **알고리즘 판정** — 확정된 응답에 RoB 2 알고리즘을 적용해 도메인·전체 판정을 산출하고, 어느 응답이 판정을 결정했는지와 무엇이 바뀌면 판정이 바뀌는지 표시
- **효과 유형 선택** — 배정 효과(ITT)와 순응 효과(PP) 중 리뷰가 보려는 효과를 첫 논문에서 한 번 선택
- **엑셀 결과 저장** — 학생·AI·최종 응답과 불일치 사유, 근거 위치, 공식 RoB 2 Excel 도구 스타일의 신호등(색 아이콘 + 도메인별 분포 차트)을 보존. 논문 1편이 끝날 때마다 자동 저장·누적
- **이어가기** — 저장된 엑셀을 올리면 중단한 도메인부터 재개

## 설치 및 사용 방법

1. literature-appraisal-rob2.skill 다운로드
2. Claude.ai → 대화창 "+" 클릭 → 스킬 클릭 → 스킬 관리 클릭 → "추가" 클릭 → "스킬 업로드" 클릭 → 다운로드 받은 스킬 업로드
3. 새 대화에 RCT 논문 PDF 1편을 첨부하고 "+" 클릭 후 스킬 선택 후 Enter
4. AI가 정리한 논문 개요를 확인 — 다르면 고쳐 줌
5. 효과 유형(배정 효과 / 순응 효과) 선택 — 특별한 이유가 없으면 배정 효과
6. 도메인마다 나타나는 입력 폼에서 "어디를 보세요"를 참고해 응답과 근거(페이지)를 적고 "계속" 클릭
7. AI 응답과 다른 문항은 해설을 읽고 최종 응답 결정
8. 도메인 판정과 전체 판정 확인 — 이의가 있으면 이유를 적어 변경 가능
9. 논문 1편이 끝나면 엑셀이 자동 전달 — 다음 논문을 첨부해 이어가고, 모두 마치면 "끝" 입력

대화가 끊기면 새 대화에 최신 엑셀과 PDF를 첨부하고 "이어서 해주세요."라고 요청합니다. 엑셀의 `_기록` 시트는 이어가기용이므로 편집하거나 삭제하지 마세요.

## 사용 시 유의사항

- 학생이 먼저 판단하고 최종 결정합니다. AI 응답은 학습과 검토를 돕는 자료이며, 원문에서 근거를 확인하세요.
- 개인 단위로 무작위 배정한 평행군 RCT만 평가합니다. 군집 무작위·교차 설계·비무작위 연구는 평가하지 않습니다.
- 질평가는 연구당 1회입니다. RoB 2는 원래 결과(outcome)별로 평가하는 도구이므로, 결과에 따라 답이 달라질 수 있는 문항은 논문의 주 종속변수를 기준으로 합니다.
- 도메인·전체 판정은 RoB 2 알고리즘을 그대로 적용한 결과입니다. 원 도구에서 평가자 재량으로 두는 "Some concerns 다수 → High" 상향은 이 학습 버전에서는 적용하지 않습니다.
- 신호질문은 원 도구를 요약·의역한 것입니다. 평가 시 원본 문서(riskofbias.info)를 함께 참조하세요.
- 학생 응답과 AI 응답의 일치율은 정확도나 검증된 독립 평가의 지표가 아닙니다. 과제·논문에는 생성형 AI 보조 사실과 RoB 2 버전(2019-08-22)을 명시하세요.

## 인용 및 출처

연구에 이 도구를 사용하셨다면 RoB 2 원 논문을 인용해 주세요:

Sterne JAC, Savović J, Page MJ, Elbers RG, Blencowe NS, Boutron I, et al. RoB 2: a revised tool for assessing risk of bias in randomised trials. BMJ 2019;366:l4898. doi: 10.1136/bmj.l4898

이 스킬 자체를 인용하실 때는 아래 형식을 사용해 주세요(필요시):

Park S., Choe J., Woo K. (2026). literature-appraisal-rob2: A Claude skill for learning RoB 2 risk-of-bias assessment of randomized trials (Version 1.0) [Computer software]. ANDA Lab, Seoul National University College of Nursing. https://doi.org/10.5281/zenodo.XXXXXXXX

RoB 2 도구(가이던스 문서·cribsheet, 2019년 8월 22일 버전)는 RoB 2 Development Group이 Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 (CC BY-NC-ND 4.0) 라이선스로 배포합니다. 이 스킬은 해당 도구의 신호질문과 알고리즘을 요약·의역해 학습용으로 재구성한 독립 구현물이며, Cochrane 및 RoB 2 Development Group의 공식 승인을 받은 것은 아닙니다. 원본: https://www.riskofbias.info

## 라이선스

소스 코드 및 스킬 문서: MIT License © 2026 Soyeon Park
RoB 2 도구 내용(`references/rob2_tool.md`, `references/rob2_teaching.md`에 요약된 신호질문·알고리즘): © RoB 2 Development Group, CC BY-NC-ND 4.0 — 비영리 목적에 한하며 원 출처를 표기해야 합니다.

## 제작자

박소연 (Soyeon Park) — 서울대학교 간호대학 박사과정 · 스킬 설계·개발

rnsy1029@snu.ac.kr

## 검토

최정인 (Jeongin Choe) — 서울대학교 간호대학 박사과정 · 검토·개선

nncj91@snu.ac.kr

## 지도교수

우경미 (Kyungmi Woo) — 서울대학교 간호대학 부교수

ANDA Lab: https://andalab.snu.ac.kr/

## 감사의 말

이 도구는 AI 도구(Claude, Anthropic)를 활용하여 개발되었습니다. 모든 설계 결정, 요구사항 정의 및 검증은 제작자가 수행했습니다.

---

# RoB 2 Quality Appraisal — Claude Skill (English)

A Claude skill for undergraduate nursing students to learn RoB 2, the Cochrane risk-of-bias tool for randomized trials, directly inside the conversation. Upload an RCT paper and the signalling questions for the five domains appear as input forms in the chat; the student answers first, then compares with the AI response. For items where the answers differ, the skill explains the concept, the relevant sentence in the paper, the reason for the response, and the common point of confusion. Domain and overall judgements are derived by the RoB 2 algorithm with the path shown, and results are saved to Excel with a traffic-light sheet.

![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)
![Claude Skill](https://img.shields.io/badge/Claude-Skill-orange.svg)
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.XXXXXXXX.svg)](https://doi.org/10.5281/zenodo.XXXXXXXX)

## Features

- **Automatic study summary** — Participants, intervention/comparator, primary dependent variable, statistical methods and trial registration are read by the AI and confirmed by the student
- **Domain guidance** — For each of the five domains: why it matters, where in the paper to look for each signalling question, and common pitfalls, shown alongside the input form
- **Student responds first** — The student enters a response and evidence (page) for each signalling question before seeing the AI response. Later items open only after earlier responses are confirmed
- **Explanation of disagreements** — Only items with different answers are explained, in four steps: concept, sentence in the paper, reason for the response, source of confusion. The student makes the final decision
- **Algorithmic judgements** — Domain and overall judgements are derived from confirmed responses using the RoB 2 algorithm, showing which response determined the judgement and what would change it
- **Effect of interest** — Choose between the effect of assignment (ITT) and the effect of adherence (PP) once, with the first paper
- **Excel results** — Keeps student, AI and final responses with reasons for disagreement, evidence locations, and a traffic-light in the style of the official RoB 2 Excel tool (coloured icons plus a per-domain distribution chart). Saved and accumulated automatically after each paper
- **Resume** — Upload a saved Excel file to continue from the last completed domain

## Installation & Usage

1. Download literature-appraisal-rob2.skill
2. In Claude.ai, click "+" in the chat box → Skills → Manage skills → Add → Upload skill → upload the downloaded file
3. In a new chat, attach one RCT paper (PDF), click "+", select the skill and press Enter
4. Check the study summary the AI has prepared — correct it if needed
5. Choose the effect of interest (assignment / adherence) — assignment unless there is a specific reason
6. For each domain, use "where to look" in the input form to find the evidence, enter your response and page number, and click Continue
7. For items where the AI response differs, read the explanation and confirm your final response
8. Review the domain and overall judgements — you can change one by recording a reason
9. After each paper, the Excel file is delivered automatically — attach the next paper to continue, and type "끝" (done) when finished

If the chat is interrupted, attach the latest Excel file and the PDF in a new chat and ask to continue. The `_기록` sheet in the Excel file is the resume record; do not edit or delete it.

## Notes on Use

- The student decides first and makes the final decision. The AI response is a learning and review aid; check the evidence in the full text.
- Only individually randomized parallel-group RCTs are appraised. Cluster-randomized, crossover and non-randomized studies are not.
- Appraisal is performed once per study. RoB 2 is designed to be applied per outcome; items whose answer may depend on the outcome are answered with reference to the paper's primary dependent variable.
- Domain and overall judgements apply the RoB 2 algorithm as published. The reviewer's discretion in the original tool to upgrade "multiple Some concerns" to High is not applied in this learning version.
- Signalling questions are summaries and paraphrases of the original tool. Refer to the original documents (riskofbias.info) when appraising.
- The agreement rate between student and AI responses is not a measure of accuracy or of a verified independent assessment. State the use of generative AI assistance and the RoB 2 version (22 August 2019) in assignments and manuscripts.

## Citation & Attribution

If you use this tool in your research, please cite the original RoB 2 publication:

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

## Reviewer

Jeongin Choe (최정인) — Doctoral Student, College of Nursing, Seoul National University · Review and improvement

nncj91@snu.ac.kr

## Advisor

Kyungmi Woo (우경미) — Associate Professor, College of Nursing, Seoul National University

ANDA Lab: https://andalab.snu.ac.kr/

## Acknowledgements

Developed with the assistance of AI tools (Claude, Anthropic). All design decisions, requirements, and validation were performed by the author.
