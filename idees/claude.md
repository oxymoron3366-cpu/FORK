# Idées de CLAUDE — Phase 1 (à l'aveugle)

Date : 2 octobre 2026. Je n'ai pas lu idees/astra.md.

Méthode : je suis parti (a) des capacités apparues en 2025-2026 qui n'ont pas encore leur « forme simple » pour Ghali, et (b) de la journée de Ghali et Alex. Pour chaque idée : le test Ghali complet, mes recherches web (requêtes, résultats, liens), et une note honnête sur les 9 non-négociables (✓ passe, ~ fragile, ✗ rate).

Rappel du contexte vérifié : Jev (TypeSafe AI) est sorti le 15 septembre 2026. Il répond à des questions fermées par des probabilités typées, 0,042 $ par million de tokens en entrée, sortie gratuite (≈ 80 000 appels pour 1 $), 70 à 500 ms par décision. Sources : https://jevtypesafeai.com/ , https://www.firecrawl.dev/blog/what-is-jev , https://www.eesel.ai/blog/typesafe-jev-pricing , https://www.marktechpost.com/2026/09/23/a-coding-guide-to-typesafe-ai-jev/ . Conséquence pour nous : juger n'importe quoi, instantanément, ne coûte plus rien. C'est la brique commune à plusieurs de mes idées.

---

## IDÉE 1 — « Le Bouclier » (bouton « Vrai ? »)

### La phrase de 5 secondes
Une IA qui te prévient, en une seconde, quand quelqu'un ou quelque chose essaie de t'avoir : arnaque, fausse vidéo, pub qui manipule, message qui te met la pression.

### La scène (mardi ordinaire)
Ghali reçoit un SMS « Votre colis est bloqué, payez 1,99 € ». Il appuie sur « Vrai ? » (bouton de partage, comme « Envoyer à… »). Réponse : « Arnaque : 97 %. Pourquoi : lien hors du site de La Poste, urgence artificielle. » Le midi, une vidéo d'un ministre circule dans le groupe famille. « Vrai ? » → « Généré par IA : 81 %. » Le soir, un site d'abonnement : « Manipulation : 74 % — le bouton "non merci" est caché, le prix affiché n'est pas le prix total. »
Pourquoi il revient le lendemain : parce que les attaques reviennent tous les jours. En 2026, un adulte reçoit plusieurs sollicitations trompeuses par jour (SMS, appels, pubs, vidéos). La version complète est un calque permanent sur l'écran : il n'a même plus à appuyer.

### Ce que ça permet qui était impossible avant
Avoir, pour chaque chose qui t'arrive dans la journée, un avis instantané et chiffré sur « est-ce honnête ? ». Avant, ça demandait un expert (impossible pour un SMS à 1,99 €) ou un appel LLM à plusieurs centimes et plusieurs secondes (trop cher pour tout vérifier). Avec Jev, 10 000 vérifications par jour et par personne coûtent 0,12 $.

### La capacité nouvelle (2025-2026) et pourquoi l'IA est nécessaire
- Jugement quasi gratuit et instantané (Jev, septembre 2026).
- Les LLM détectent les manipulations conversationnelles : « AI Watchdog » (arXiv 2608.21841, août 2026) classe en temps réel 5 familles de manipulation (flatterie, biais de marque, dissimulation…) avec un modèle à poids ouverts : https://arxiv.org/abs/2608.21841
- Le problème a changé d'échelle : GPT-4 avec quelques infos personnelles est plus persuasif qu'un humain dans 64,4 % des débats (Salvi et al., Nature Human Behaviour 2025) : https://arxiv.org/abs/2403.14380v1 . Les vidéos et voix synthétiques sont devenues indiscernables. Autrement dit : les attaquants ont déjà l'IA ; les gens normaux, non.
Un programme simple suffirait-il ? Non : les listes noires et les règles (filtres anti-spam) ratent toute attaque nouvelle ou personnalisée. Il faut comprendre le texte, l'image, le contexte.

### Ce qui existe déjà (recherches faites)
Requêtes : « AI app detects manipulation in messages ads dark patterns real time consumer », « Google scam detection Messages Pixel 2025 Norton Genie Bitdefender Scamio », « browser extension AI detects dark patterns manipulation for consumers 2025 2026 ».
Trouvé :
- Google Scam Detection (Pixel, mars 2025) : SMS et appels, sur l'appareil, Pixel seulement : https://blog.google/security/new-ai-powered-scam-detection-features/
- Extensions navigateur « dark patterns » : Pattern Shield (Chrome), Dark Radar (Firefox), projet Dark Pita (Notre Dame), capstone Berkeley 2026 : https://www.ischool.berkeley.edu/projects/2026/deceptive-pattern-detector , https://engineering.nd.edu/news/ai-browser-plug-ins-to-help-consumers-improve-digital-privacy-literacy-combat-manipulative-design/
- AI Watchdog (prototype de recherche, seulement pour les conversations avec des chatbots).
- FairPatterns (B2B, pour les entreprises qui veulent se mettre en règle) : https://www.fairpatterns.ai/
Je n'ai pas trouvé de produit grand public qui couvre TOUT (arnaques + faux contenus + manipulation commerciale + pression dans les messages), sur tout ce que tu reçois, avec une probabilité calibrée et un « pourquoi ». Ce qui existe est découpé par type d'attaque et par canal.

### Pourquoi « prochain ChatGPT » et pas une fonction ajoutée par un géant
Argument structurel, pas technique : Google (environ 265 milliards de dollars de pub en 2024) et Meta (environ 160 milliards) vivent de la persuasion payante. Ils ne peuvent pas livrer un produit dont le travail est d'étiqueter « manipulation : 74 % » sur les pubs de leurs propres clients. C'est le même blocage que Google face à ChatGPT (cannibaliser la recherche). Apple pourrait, mais Apple ne voit ni tes SMS WhatsApp ni tes vidéos TikTok. Et c'est une nouvelle catégorie : après « l'IA qui répond » et « l'IA qui agit », « l'IA qui te défend » — l'antivirus du cerveau, à l'ère où toutes les attaques sont faites par IA.

### La démo rapide (un jour)
Une page web + raccourci de partage : on colle un texte, une capture d'écran, un lien ou une vidéo. Trois questions à Jev (arnaque ? manipulation ? généré par IA ?) + un LLM qui écrit 3 lignes de « pourquoi ». Résultat en moins de 2 secondes.
Laissé de côté : le calque permanent sur l'écran, les appels vocaux en direct, la détection de deepfake vidéo de qualité (on s'appuierait sur des services existants au début), le mode « famille » (protéger les parents âgés).

### L'argent
Abonnement type antivirus (Norton compte des dizaines de millions d'abonnés payants pour un problème moins fréquent). Plan famille (« je protège mes parents »). Jamais de pub : c'est précisément la raison d'exister du produit.

### Abus et risques
- Faux positifs sur des humains : si le Bouclier dit « ton partenaire te manipule : 62 % », il casse un couple. Règle : il juge des messages, pas des personnes, et il explique toujours « pourquoi » pour qu'on puisse le contredire.
- Course aux armements : les arnaqueurs testent leurs textes contre le Bouclier pour passer dessous. Réponse : modèle mis à jour en continu, et signalements des utilisateurs.
- Vie privée : il lit tout. Il faut une version sur l'appareil (AI Watchdog montre que c'est possible avec des poids ouverts).
- Paranoïa : tout devient suspect. Réponse : calibration affichée (« quand je dis 90 %, j'ai raison 9 fois sur 10 »).
- Capture : un Bouclier acheté par un annonceur. Réponse : modèle vérifiable, pas de revenu publicitaire.

### Note sur les non-négociables
1 ✓ (moat structurel) · 2 ✓ · 3 ~ (la partie « arnaque SMS » existe chez Google ; le tout unifié, je ne l'ai pas trouvé) · 4 ✓ · 5 ✓ · 6 ✓ · 7 ✓ · 8 ✓ · 9 ✓.
Point faible à débattre : est-ce « un meilleur antivirus » ou une nouvelle catégorie ?

---

## IDÉE 2 — « L'Accord »

### La phrase de 5 secondes
Chacun dit en privé ce qu'il veut, et l'IA écrit la proposition que tout le groupe accepte.

### La scène (mardi ordinaire)
Groupe WhatsApp « Famille », 9 personnes, anniversaire de la grand-mère : 140 messages, personne ne décide. Alex envoie un lien L'Accord. Chacun répond à une question en 30 secondes (« qu'est-ce qui compte pour toi ? budget, date, lieu… »). L'IA écrit : « Samedi 18, chez tante Nadia, repas partagé, 15 € par personne, les enfants dorment sur place. » Chacun appuie ✓ ou écrit une objection. Deuxième tour : c'est réglé. 4 minutes.
Pourquoi il revient le lendemain : les colocs pour le ménage, les amis pour le week-end, le couple pour « on mange quoi », les parents d'élèves pour la sortie. Les groupes décident mal tous les jours.

### Ce que ça permet qui était impossible avant
Un texte qui maximise l'accord de tout le monde, en gardant les avis minoritaires, écrit mieux qu'un médiateur humain. Avant : soit un vote (qui écrase la minorité), soit 140 messages.

### La capacité nouvelle et pourquoi l'IA est nécessaire
La « Habermas Machine » (Google DeepMind, Science, octobre 2024, plus de 5 000 participants) : un modèle génère des énoncés de groupe, un second prédit comment chaque participant les classera, on garde celui qui est le plus largement accepté. Les énoncés IA ont été préférés à ceux de médiateurs humains, et les groupes ont davantage convergé : https://www.science.org/doi/10.1126/science.adq2852 (copie : https://www.rivista.ai/wp-content/uploads/2024/10/science.adq2852.pdf ). Un programme simple (Doodle) ne fait que choisir une date ; il n'écrit pas une proposition qui réconcilie des envies différentes. Jev rend la partie « prédire l'acceptation de chacun » presque gratuite.

### Ce qui existe déjà (recherches faites)
Requêtes : « Habermas Machine DeepMind consensus app consumer group decision product 2025 », « AI mediator app for group chat family friends decide together consensus », « Habermas Machine open source implementation app consumer ».
Trouvé :
- Habermas Machine : recherche, « en discussion avec des partenaires » pour un déploiement (civique, pas grand public) : https://knightcolumbia.org/content/can-ai-mediation-improve-democratic-deliberation
- « Habermolt » (arXiv 2605.24413, mai 2026) : déléguer la délibération à des représentants IA, recherche : https://arxiv.org/pdf/2605.24413
- ProMediate (Microsoft Research) : médiateur proactif dans une conversation à plusieurs, recherche : https://www.microsoft.com/en-us/research/articles/evaluating-proactive-ai-mediators-in-multi-party-conversation-with-promediate/
- Applis de conflit : Mediator App (concours Gemini), Auralink, « Who's Right? » (couples) : https://ai.google.dev/competition/projects/mediator-app , https://play.google.com/store/apps/details?id=com.artiqulate.artiqulate
- Outils civiques ou B2B : Polis, Remesh, Talk to the City.
Je n'ai pas trouvé d'outil grand public pour les décisions ordinaires de groupe (pas les conflits, pas la politique) qui produise la proposition acceptable par tous en une minute.

### Pourquoi « prochain ChatGPT »
ChatGPT, c'est « moi et la machine ». L'Accord, c'est « nous et la machine » : la première IA dont l'unité de base est le groupe. Risque honnête : Meta pourrait l'ajouter à WhatsApp. Contre-argument : Meta AI dans les groupes est un chatbot, pas un mécanisme de décision ; et L'Accord marche par lien, dans n'importe quelle messagerie. Mais ce risque reste le point le plus fragile de l'idée.

### La démo rapide
Un lien, N personnes répondent à une question, un LLM génère 5 propositions, Jev note la probabilité d'acceptation de chaque personne pour chaque proposition (5 × N appels, quasi gratuit), on garde celle qui a le pire score le plus haut (protège la minorité), un tour d'objections, proposition finale.
Laissé de côté : l'intégration dans WhatsApp, la mémoire du groupe (« la dernière fois, c'était chez toi »), les grands groupes (immeuble, association, commune).

### L'argent
Gratuit pour les petits groupes. Payant pour les grands (copropriétés, clubs, écoles, associations) : ce sont encore des gens normaux qui décident ensemble, pas des entreprises. Plan famille.

### Abus et risques
- Réponses stratégiques : quelqu'un exagère pour tirer la proposition vers lui. Réponse : le choix « max-min » et le tour d'objections limitent le gain ; et on peut afficher « cette proposition s'éloigne de toi de X » à chacun.
- Fuite indirecte : si une seule personne est végétarienne, la proposition la trahit. Réponse : prévenir avant de répondre, et laisser marquer une réponse « ne pas rendre identifiable ».
- Pression du groupe : « l'IA a dit ». Réponse : la proposition s'appelle « proposition », jamais « décision » ; elle ne vaut qu'après les ✓ humains.
- Paresse : on ne se parle plus. C'est vrai, et c'est le prix de tout outil de coordination.

### Note sur les non-négociables
1 ~ (risque « fonction WhatsApp ») · 2 ✓ · 3 ✓ (théorie + prototypes, pas de forme grand public trouvée) · 4 ✓ · 5 ✓ · 6 ✓ · 7 ✓ · 8 ~ · 9 ✓.

---

## IDÉE 3 — « Et si ? » (le Pré-vu)

### La phrase de 5 secondes
Avant d'envoyer, d'acheter ou de dire quelque chose, tu vois en une seconde ce qui va probablement se passer.

### La scène (mardi ordinaire)
Alex écrit à son propriétaire : « C'est inadmissible, la chaudière est en panne depuis 10 jours. » Il appuie sur « Et si ? ». Réponse : « Répond dans la semaine : 55 % · Ignore : 30 % · S'énerve : 15 %. Le mot "inadmissible" fait monter "ignore". Sans ce mot : 68 / 22 / 10. » Le soir : « Et si j'achète ces baskets ? » → « Regret dans 30 jours : 41 % (tu as déjà 2 paires similaires). » Le lendemain : avant de poster une photo, avant d'accepter une invitation, avant de répondre à sa mère.
Pourquoi il revient : parce qu'on prend 100 micro-décisions par jour et qu'on en regrette plusieurs. Et parce que l'outil apprend : il demande le lendemain « alors, il a répondu ? » et devient plus juste pour toi.

### Ce que ça permet qui était impossible avant
Voir une distribution chiffrée des conséquences d'un acte ordinaire, calibrée pour toi, avant de le faire. Avant : demander à un ami (lent, pas chiffré), ou rien.

### La capacité nouvelle et pourquoi l'IA est nécessaire
- GPT-4 prédit les résultats de 70 expériences de sciences sociales avec r = 0,85, y compris des études non publiées (Hewitt et al., 2024) : https://www.gsb.stanford.edu/index%2ephp/node/630911
- Des agents construits sur 2 heures d'entretien reproduisent les réponses d'une personne à 85 % (Park et al., Stanford, novembre 2024) : https://arxiv.org/pdf/2411.10109
- Jev rend la probabilité calibrée instantanée et gratuite.
Un programme simple ne peut pas prédire la réaction d'un propriétaire à un mot.

### Ce qui existe déjà (recherches faites)
Requêtes : « app predicts how recipient will react to your message before sending AI probability », « Mei messaging app AI relationship analysis contacts personality ».
Trouvé :
- ReTalk (Google Play, Corée) : donne 3 scénarios de réponse (pire, moyenne, meilleure) avec un style de destinataire choisi à la main : https://play.google.com/store/apps/details?id=net.lateinit.retalk&hl=en_US
- Mei (2018-2019) : profils psychologiques des contacts à partir des SMS, conseils de réponse : https://venturebeat.com/ai/mei-uses-ai-to-improve-relationships-by-analyzing-text-messages
- Plusieurs brevets américains sur la prédiction de réaction du destinataire (ex. US 10796236, US 12166809) : https://image-ppubs.uspto.gov/dirsearch-public/print/downloadPdf/10796236
- Détecteurs de ton (Grammarly, outils d'écriture Apple) : ils qualifient ton texte, ils ne prédisent pas l'autre.
Je n'ai pas trouvé de produit qui donne des probabilités calibrées, pour tout type d'acte (pas seulement les messages), et qui se recalibre avec ce qui s'est vraiment passé. C'est donc « en théorie et en petits prototypes ».

### Pourquoi « prochain ChatGPT »
ChatGPT répond à « qu'est-ce que c'est ? ». Et si ? répond à « qu'est-ce qui va se passer si je… ? » : une couche de prévoyance sur la vie. Risque honnête : Apple ou Google peuvent le mettre dans le clavier. Contre-argument partiel : les plateformes gagnent quand tu envoies, postes et achètes PLUS ; un outil qui te dit « regret : 41 % » va contre leur intérêt. Mais c'est moins solide que pour le Bouclier.

### La démo rapide
Clavier ou page web : on colle le message et on dit à qui c'est destiné (ou l'achat, ou la décision). Jev donne les probabilités sur 4 à 6 issues, un LLM explique en une phrase et propose une variante. Le lendemain, une question : « que s'est-il passé ? » pour recalibrer.
Laissé de côté : l'intégration clavier système, la mémoire longue des personnes de ta vie, les actes non textuels.

### L'argent
Abonnement ; pas de pub.

### Abus et risques
- Devenir un outil de manipulation : « quels mots pour qu'elle dise oui ? » C'est exactement le danger de Salvi 2025. Garde-fou : l'outil prédit, il n'optimise pas contre une personne (refus des demandes « pour qu'il cède »), et il affiche aussi « comment l'autre va se sentir ».
- Anxiété et dépendance : ne plus rien envoyer sans vérifier.
- Prophétie auto-réalisatrice et fausse confiance. Réponse : calibration affichée, et « je ne sais pas » quand il manque le contexte.
- Vie privée : il lit tes messages.

### Note sur les non-négociables
1 ~ · 2 ✓ · 3 ~ (ReTalk, Mei, brevets) · 4 ✓ · 5 ~ (le regret est universel, mais est-ce « hyper important » ?) · 6 ✓ · 7 ✓ · 8 ✓ · 9 ✓.
Possible fusion avec l'idée 1 : un seul produit, deux boutons — « Vrai ? » pour ce qui t'arrive, « Et si ? » pour ce que tu vas faire.

---

## IDÉE 4 — « Le Double »

### La phrase de 5 secondes
Deux heures de conversation, et tu as une copie de toi qui répond à ta place.

### La scène (mardi ordinaire)
Ghali a fait son entretien de 2 heures le week-end. Mardi : son double répond au questionnaire du médecin, au sondage de la mairie, à « tu viens samedi ? » du groupe de foot (« Ghali : probablement oui si c'est après 18 h »), au service client de l'opérateur. Ghali ne voit qu'un résumé le soir, et corrige en deux mots. Il demande aussi à son double : « est-ce que je regretterais de déménager à Lyon ? » et le double répond comme lui, avec les raisons.
Pourquoi il revient : il ne « revient » pas, le double travaille pendant qu'il vit. Chaque correction le rend plus fidèle.

### Ce que ça permet qui était impossible avant
Être à plusieurs endroits à la fois, pour toutes les questions ordinaires qu'on te pose, sans que ce soit un chatbot générique : c'est TOI à 85 %.

### La capacité nouvelle et pourquoi l'IA est nécessaire
Park et al. (Stanford, 2024) : 1 052 personnes, 2 heures d'entretien chacune, les agents reproduisent leurs réponses à 85 % (autant que les personnes elles-mêmes à deux semaines d'intervalle) : https://arxiv.org/pdf/2411.10109 ; résumé HAI : https://nervegna.substack.com/p/stanford-hais-1000-person-ai-simulation . Impossible sans LLM.

### Ce qui existe déjà (recherches faites)
Requêtes : « Stanford generative agent simulations 1000 people digital twin consumer app », « Delphi digital clone Personal.ai AI twin that answers questions on your behalf », « Volar Teaser AI dating app AI clones date each other Bumble AI concierge ».
Trouvé :
- Delphi : clones d'experts et de créateurs, pour vendre leur savoir : https://venturebeat.com/ai/you-can-now-make-an-ai-clone-of-yourself-or-anyone-else-living-or-dead-with-delphi
- Personal.ai : mémoire personnelle, « version de toi » : https://davidriha.com/blog/best-tools-create-ai-double-2026/
- Volar (2024) : des clones qui font les premiers rendez-vous amoureux à ta place : https://www.globaldatinginsights.com/news/volar-where-ai-avatars-go-on-first-dates-for-you/ ; concept « concierge » de Bumble : https://fortune.com/2024/05/10/bumbles-whitney-wolfe-herd-dating-concierge-artificial-intelligence
- Habermolt (2026) : représentants IA dans la délibération (recherche).
Donc : existe en théorie (Stanford) et en prototypes de niche (créateurs, rencontres). Je n'ai pas trouvé la forme « pour tout le monde, pour toutes les questions ordinaires, construit en 2 heures ».

### Pourquoi « prochain ChatGPT »
« Une IA qui sait tout » (ChatGPT) → « une IA qui est moi ». Potentiellement plus grand : chaque humain a son double, et les doubles se parlent (c'est le moteur de L'Accord, idée 2). Risque : c'est aussi ce que OpenAI vise avec la mémoire. Mais la mémoire de ChatGPT sert ChatGPT ; le Double te représente ailleurs.

### La démo rapide
Un entretien vocal de 20 minutes (au lieu de 2 heures), puis une page « demande à mon double » que tes amis peuvent utiliser, et un mode « demande-toi à toi-même ».
Laissé de côté : la connexion aux formulaires et services réels, le mode privé/public fin, l'apprentissage par corrections.

### L'argent
Abonnement ; et, plus tard, les services qui préfèrent interroger ton double plutôt que t'envoyer un formulaire paient pour cela (avec ton accord et ta part).

### Abus et risques (les plus lourds de mes 5 idées)
- Attaque par simulation : si quelqu'un a accès à ton double, il peut tester mille arguments dessus pour trouver celui qui te fait céder (Salvi 2025 + Stanford 2024 = la recette). Règle absolue : le double n'est jamais exposé brut ; les autres ne voient que des réponses à des questions précises, avec limite et traçabilité.
- Usurpation et consentement : un double sans ton accord, un double de mort, un employeur qui exige ton double.
- Dérive d'identité : les clones Volar ont inventé des goûts qui n'étaient pas ceux de leurs humains.
- Proximité avec le cimetière n° 5 (simuler une société) : je le signale moi-même. Différence : ici c'est un individu, pour lui-même, pas une foule synthétique vendue à des entreprises.

### Note sur les non-négociables
1 ✓ · 2 ~ (c'est le double qui travaille, pas Ghali) · 3 ~ (prototypes de niche) · 4 ✓ · 5 ~ · 6 ✓ · 7 ✓ · 8 ✓ · 9 ✓.

---

## IDÉE 5 — « Le Procès »

### La phrase de 5 secondes
Pose n'importe quelle question : deux IA se battent 60 secondes, une troisième tranche avec un pourcentage.

### La scène (mardi ordinaire)
Alex hésite : « je passe à la voiture électrique ? » Il lance le procès. L'accusation et la défense ont chacune 30 secondes, avec des sources. Le juge : « Pour toi, oui : 63 %. Point décisif : tu n'as pas de prise de recharge chez toi. » Le soir, entre amis : « l'ananas sur la pizza ? » — procès, rires, partage de l'extrait.
Pourquoi il revient : les petites et grandes décisions sont quotidiennes, et le format est amusant à partager.

### Ce que ça permet qui était impossible avant
Avoir les deux meilleurs avocats du monde sur n'importe quelle question, en une minute, et un verdict qui n'est pas la voix unique et complaisante d'un chatbot.

### La capacité nouvelle et pourquoi l'IA est nécessaire
Le débat entre IA rend les humains plus justes : +4 à +10 % de précision, jusqu'à +15,2 % sur des affirmations sur le Covid (Rahman et al., 2025) : https://arxiv.org/abs/2506.02175 ; et des débatteurs plus persuasifs mènent à des réponses plus vraies (Khan et al., 2024, résumé Quanta) : https://www.quantamagazine.org/debate-may-help-ai-models-converge-on-truth-20241108/ . Le verdict chiffré vient de Jev.

### Ce qui existe déjà (recherches faites)
Requête : « two AIs debate both sides question judge consumer app AI debate settle argument 2025 ».
Trouvé :
- GavelBot : des humains débattent, l'IA juge : https://gavelbot.com/
- Un outil IA-contre-IA (prototype, EA Forum) : GPT-4o, Gemini, Grok tirés au sort pour chaque camp : https://forum.effectivealtruism.org/posts/JRGW8kEqFLhDHjmLe/an-ai-vs-ai-debate-tool-to-surface-strong-arguments-and-test
- Deb8flow (démo de développeur), Junia (générateur d'arguments), Levelheaded (litiges juridiques, oct. 2026).
Je n'ai pas trouvé de produit grand public « procès en 60 secondes avec verdict chiffré » pour les questions de la vie ordinaire. Mais c'est l'idée la plus proche d'une simple fonction.

### Pourquoi « prochain ChatGPT » — honnêtement, c'est fragile
La promesse « la fin de l'IA à voix unique » est forte, mais OpenAI ou Google peuvent ajouter un mode « débat » en une semaine. Je garde l'idée pour le format (viral, simple) et comme brique possible des autres (le Bouclier peut « faire le procès » d'une pub).

### La démo rapide
Deux appels LLM (pour / contre, avec recherche web), un appel Jev pour le verdict, une page qui rejoue le procès en texte ou en voix.
Laissé de côté : la personnalisation au contexte d'Alex, les extraits vidéo partageables.

### L'argent
Abonnement ; version gratuite limitée.

### Abus et risques
- Faux équilibre : un procès « les vaccins causent-ils l'autisme ? » donne l'impression d'un débat ouvert. Réponse : le verdict est calibré et cite les sources ; mais le risque existe (Rahman montre que le débat aide, pas qu'il est sans danger).
- Procès de personnes : « Untel est-il un menteur ? » — leçon Sarahah. Interdiction stricte des procès visant des personnes privées.
- Gamification de la vérité.

### Note sur les non-négociables
1 ✗/~ · 2 ~ · 3 ~ · 4 ✓ · 5 ~ · 6 ✓ · 7 ✓ · 8 ~ · 9 ✓.

---

## Mon classement provisoire (avant débat)
1. Le Bouclier — seul à avoir un argument structurel contre « un géant l'ajoute en une semaine » (le conflit avec la pub). Point à prouver : nouvelle catégorie, pas « meilleur antivirus ».
2. L'Accord — le plus « seulement en théorie » (Science 2024, pas de forme grand public trouvée) et le plus nouveau comme catégorie (« nous et la machine »). Point à prouver : résister à une fonction WhatsApp.
3. Et si ? — très quotidien, très simple ; fragile sur l'existant (ReTalk, Mei) et sur « hyper important ». Candidat à fusion avec le Bouclier.
4. Le Double — potentiel immense, risques les plus lourds, usage quotidien indirect.
5. Le Procès — format fort, mais probablement une fonction.

Ce que je demanderai à ASTRA de démolir en priorité : l'argument « conflit avec la pub » du Bouclier, et le risque « fonction WhatsApp » de L'Accord.

FIN-IDEES
