# Literature Review

## Introduction

Meal planning remains a time-consuming task for households and individuals. Inefficient use of available ingredients leads to food waste, unnecessary expenses, and suboptimal dietary choices. Existing research in food recommender systems and personalized nutrition has made significant progress in generating meal plans based on preferences, nutritional requirements, and health conditions. However, most systems still generate recommendations “from scratch” without systematically considering what products are already available at home and within a family budget.

This literature review critically examines recent work on food recommender systems, AI-driven personalized nutrition, and constraint-based meal planning. The review identifies a clear research gap: the absence of integrated solutions that simultaneously account for available products, dietary preferences, and family budget.

## Food Recommender Systems

Bondevik et al. (2023) conducted a systematic literature review of 67 high-quality studies on food recommender systems. The majority of systems rely on content-based filtering and machine learning approaches, often providing non-personalized recommendations. The review highlights the complexity of the food domain, including cultural preferences, visual attributes, and the exponential number of possible ingredient combinations. While collaborative filtering and hybrid methods exist, few systems incorporate hard constraints such as ingredient availability or cost.

Zada et al. (2025) performed a large-scale systematic review and meta-analysis of dynamic nutrient profiling for personalized diet planning (117 studies, 45,672 participants). AI-enhanced systems demonstrated superior effectiveness compared to traditional algorithmic approaches in improving dietary quality and adherence. However, the review notes practical limitations related to technological accessibility and a lack of focus on everyday household constraints.

## AI and Generative Approaches

Papastratis et al. (2024) proposed a deep generative model (variational autoencoder) combined with ChatGPT to generate weekly meal plans aligned with nutritional guidelines. The system models user anthropometric data and medical conditions and uses an optimizer to adjust meal quantities. While the approach achieves high accuracy on energy and nutrient targets, it does not consider existing pantry items or budget limitations.

Gavai and van Hillegersberg (2025) introduced a RAG-based system using a locally deployed LLaMA3 model for personalized smoothie recipes targeting obesity and type 2 diabetes. The “virtual nutritionist” iteratively validates recipes against nutritional and sustainability criteria. The system includes a web prototype and emphasizes explainability, but remains focused on clinical conditions rather than general household meal planning with available ingredients.

Tsolakidis et al. (2026) presented an AI-driven multivariate approach (PLAN’EAT Nutrition Advisor) that generates personalized weekly meal plans aligned with sustainable healthy diet food-group guidelines. The pipeline includes meal filtering, large-scale sampling, scoring against nutritional targets, and diversity optimization. The system was validated on 1,000 synthetic user profiles. Similar to other works, it does not incorporate real-time ingredient availability or cost constraints.

Soekamto et al. (2025) developed Pic2Plate, a vision-language and retrieval-augmented framework that extracts ingredients from user-uploaded images and retrieves personalized recipes. The system achieved strong performance in ingredient detection (F1-score 0.86) and recipe relevance. This work is one of the closest to pantry-aware recommendation, yet it does not address budget or multi-day planning with cost optimization.

## Knowledge-Based and Constraint-Based Systems

Stefanidis et al. (2022) presented the PROTEIN AI Advisor, a knowledge-based recommendation framework using expert-validated meals. The architecture consists of a qualitative layer (ontology and fuzzy inference) and a quantitative layer (optimization). The system achieved 92% accuracy in nutrient recommendations across multiple user groups. Amiri et al. (2023) combined ontology, fuzzy logic, heuristic search, and multicriteria decision-making for flexible meal planning under health constraints. Both systems demonstrate strong constraint handling but do not model available household products or family budget.

Zioutos et al. (2024) applied collaborative filtering combined with health history analysis for weekly meal planning, including dynamic adaptation. Kalpakoglou et al. (2025) developed the SWITCHtoHEALTHY system for family nutrition based on the Mediterranean diet, with separate recommenders for adults and children. The system supports shared family meals and was validated in a real-world intervention (90% accuracy). These works address family context but still lack integration of pantry inventory and budget.

Kopitar et al. (2025) investigated the use of large language models (Llama-3 70B and GPT-4o) for identifying and decomposing compound ingredients in meal plans. The best models achieved F1-scores above 0.84, demonstrating the potential of LLMs for ingredient-level processing. This capability is relevant for systems that need to match recipes against available products.

## Gap and Positioning of the Project

Across the reviewed literature, a consistent pattern emerges. Systems excel at personalization based on preferences, nutritional targets, and health conditions. Several works incorporate sustainability, family context, or image-based ingredient recognition. However, almost no system simultaneously optimizes for three practical constraints that are central to real household meal planning:

- Available products currently in the household (pantry / fridge),
- Dietary preferences and restrictions,
- Family budget.

This gap is particularly relevant for reducing food waste and unnecessary spending. The proposed intelligent platform addresses this gap by integrating all three factors into a single system that generates personalized meal plans and recipes.

## Conclusion

The reviewed literature provides a solid foundation in recommender system techniques, AI-driven generation, knowledge-based constraint handling, and family-oriented meal planning. The project builds upon these advances while focusing on the under-addressed combination of available ingredients, preferences, and budget. This positions the work as a practical contribution to household meal planning that can reduce both food waste and financial cost.

---

## Analysis Table

| №   | Authors, Year                              | Main Idea / Method                                                                                        | Limitations                                                                      | Relevance to the Project                                     |
| --- | ------------------------------------------ | --------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- | ------------------------------------------------------------ |
| 1   | Zada et al., 2025                          | Systematic review and meta-analysis of dynamic nutrient profiling and AI-based personalized diet planning | Focus on clinical outcomes; limited attention to household practical constraints | Justifies effectiveness of AI personalization                |
| 2   | Bondevik et al., 2023                      | Systematic review of 67 food recommender systems; predominance of content-based and ML methods            | Most systems are non-personalized and ignore pantry/budget constraints           | Taxonomy of recommendation methods                           |
| 3   | Papastratis et al., 2024                   | Deep generative model (VAE) + ChatGPT for guideline-aligned weekly meal plans                             | No consideration of available products or budget                                 | Generative approach + nutritional alignment                  |
| 4   | Gavai & van Hillegersberg, 2025            | RAG + local LLaMA3 + iterative “virtual nutritionist” for personalized recipes                            | Clinical focus (obesity/T2D); no pantry or budget                                | RAG architecture and explainability                          |
| 5   | Tsolakidis et al., 2026                    | AI + expert rules + sampling/optimization for sustainable weekly meal plans                               | No real-time ingredient availability or cost constraints                         | Multi-stage optimization pipeline                            |
| 6   | Zioutos et al., 2024                       | Collaborative filtering + health history for weekly meal plans with dynamic adaptation                    | Does not model pantry inventory or budget                                        | Dynamic adaptation idea                                      |
| 7   | Kopitar et al., 2025                       | LLMs for identifying and decomposing compound ingredients                                                 | Narrow task; not a full planner                                                  | LLM-based ingredient processing                              |
| 8   | Amiri et al., 2023                         | Ontology + fuzzy logic + heuristic search + multicriteria decision-making                                 | No pantry or budget modeling                                                     | Knowledge-based filtering and multicriteria evaluation       |
| 9   | Stefanidis et al., 2022                    | Knowledge-based framework (ontology + fuzzy inference + optimization) with expert-validated meals         | No available products or budget                                                  | Two-layer (qualitative + quantitative) architecture          |
| 10  | Kalpakoglou et al., 2025                   | AI-based family nutrition recommender (Mediterranean diet) with separate engines for adults and children  | Family context present, but no pantry or budget                                  | Family meal planning approach                                |
| 11  | Soekamto et al., 2025                      | Vision-language model + RAG for ingredient extraction from images and personalized recipe retrieval       | Limited multi-day planning and no budget optimization                            | Closest to pantry-aware recommendation via image recognition |
| 12  | [Additional source on food waste / budget] | Mathematical programming / optimization for meal planning with package sizes, cost, and waste reduction   | —                                                                                | Directly addresses cost and waste reduction through planning |

---

## References

## References

[1] M. H. M. Zada, D. Pan, and G. Sun, “A comprehensive systematic review of dynamic nutrient profiling for personalized diet planning: Meta-analysis and PRISMA-based evidence synthesis,” _Foods_, vol. 14, no. 21, Art. no. 3625, 2025, doi: 10.3390/foods14213625.

[2] J. N. Bondevik, K. E. Bennin, Ö. Babur, and C. Ersch, “A systematic review on food recommender systems,” _Expert Systems with Applications_, vol. 238, Art. no. 122166, 2024, doi: 10.1016/j.eswa.2023.122166.

[3] I. Papastratis, D. Konstantinidis, P. Daras, and K. Dimitropoulos, “AI nutrition recommendation using a deep generative model and ChatGPT,” _Scientific Reports_, vol. 14, Art. no. 14620, 2024, doi: 10.1038/s41598-024-65438-x.

[4] A. K. Gavai and J. van Hillegersberg, “AI-driven personalized nutrition: RAG-based digital health solution for obesity and type 2 diabetes,” _PLOS Digital Health_, vol. 4, no. 5, Art. no. e0000758, 2025, doi: 10.1371/journal.pdig.0000758.

[5] D. Tsolakidis, V. Stamatis, L. P. Gymnopoulos, V. Pózner, D. Szakal, A. L. Valtueña, I. Blázquez, P. S. Elliott, L. D. Devine, E. R. Gibney, A. M. O’Sullivan, and K. Dimitropoulos, “An AI-driven multivariate approach for personalized healthy eating recommendations aligned with sustainable healthy diet food-group guidelines,” _Frontiers in Nutrition_, vol. 13, Art. no. 1894893, 2026, doi: 10.3389/fnut.2026.1894893.

[6] B. Hannon, Y. Kumar, J. J. Li, and P. Morreale, “Chef Dalle: Transforming cooking with multi-model multimodal AI,” _Computers_, vol. 13, no. 7, Art. no. 156, 2024, doi: 10.3390/computers13070156.

[7] K. Zioutos, H. Kondylakis, and K. Stefanidis, “Healthy personalized recipe recommendations for weekly meal planning,” _Computers_, vol. 13, no. 1, Art. no. 1, 2024, doi: 10.3390/computers13010001.

[8] L. Kopitar, L. Bedrac, L. J. Strath, J. Bian, and G. Stiglic, “Improving personalized meal planning with large language models: Identifying and decomposing compound ingredients,” _Nutrients_, vol. 17, no. 9, Art. no. 1492, 2025, doi: 10.3390/nu17091492.

[9] M. Amiri, J. Li, and W. Hasan, “Personalized flexible meal planning for individuals with diet-related health concerns: System design and feasibility validation study,” _JMIR Formative Research_, vol. 7, Art. no. e46434, 2023, doi: 10.2196/46434.

[10] Y. S. Soekamto, A. Lim, L. C. Limanjaya, Y. K. Purwanto, S.-H. Lee, and D.-K. Kang, “Pic2Plate: A vision-language and retrieval-augmented framework for personalized recipe recommendations,” _Sensors_, vol. 25, no. 2, Art. no. 449, 2025, doi: 10.3390/s25020449.

[11] K. Stefanidis, D. Tsatsou, D. Konstantinidis, L. Gymnopoulos, P. Daras, S. Wilson-Barnes, K. Hart, V. Cornelissen, E. Decorte, E. Lalama, A. Pfeiffer, M. Hassapidou, I. Pagkalos, A. Argiriou, K. Rouskas, S. Hadjidimitriou, V. Charisis, S. Balula Dias, J. Alves Diniz, G. Telo, H. Silva, A. Bensenousi, and K. Dimitropoulos, “PROTEIN AI Advisor: A knowledge-based recommendation framework using expert-validated meals for healthy diets,” _Nutrients_, vol. 14, Art. no. 4435, 2022, doi: 10.3390/nu14204435.

[12] K. Kalpakoglou, P. Degli Innocenti, F. Bergamo, D. Beretta, F. Bergenti, A. Rosi, F. Scazzina, L. Calderón-Pérez, N. Boqué, M. Güldaş, Ç. Erdoğan Demir, L. P. Gymnopoulos, and K. Dimitropoulos, “SWITCHtoHEALTHY AI-based family nutrition recommendation system: Promoting the Mediterranean diet,” _Nutrients_, vol. 17, no. 24, Art. no. 3892, 2025, doi: 10.3390/nu17243892.
