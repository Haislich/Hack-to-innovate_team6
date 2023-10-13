# ![hack to innovate banner](https://i.ibb.co/4WJfDxC/HEADER-1400-X250-3.png)

## Hack to innovate team6

Questa è la repo del team 6 per l'hackaton organizzato da Codemotion, Hack to innovate.
In questo readme vengono affrontate in breve: I'aproccio utilizzato per questa proposta e le motivazioni tecniche che hanno portato alla scelta di un framework RAG.

-
Indice:
- [UX/UI;](https://github.com/Haislich/Hack-to-innovate_team6#uxui)
  
  - [Prototipo Figma;](https://www.figma.com/proto/PbWAJc88VYP9eUOVKwBkhn/Team-6-Hackathon?page-id=1%3A2&type=design&node-id=1-67&viewport=532%2C364%2C0.09&t=z7NDR9yp63H9OjQ7-1&scaling=scale-down&mode=design)
  
- [Approccio Tecnico;](https://github.com/Haislich/Hack-to-innovate_team6#hai-bisogno-di-una-mano-approccio-tecnico)
- [Large Language Models](https://github.com/Haislich/Hack-to-innovate_team6#large-language-models)
- [References;](https://github.com/Haislich/Hack-to-innovate_team6#references)
  - [Inclusione digitale](https://github.com/Haislich/Hack-to-innovate_team6#inclusione-digitale)
  - [Accessibilità](https://github.com/Haislich/Hack-to-innovate_team6#accessibilit%C3%A0)
  - [RAG AI & Generative AI](https://github.com/Haislich/Hack-to-innovate_team6#rag-ai--generative-ai)
  - [Altro](https://github.com/Haislich/Hack-to-innovate_team6#altro)

## UX/UI
Per affrontare questo Hackathon siamo partiti da tre punti principali:
- Focus sull’app Mobile Intesa San Paolo;
- Assenza di dati feedback degli utenti attuali dell’app;
- Difficoltà di raccolta dati da interviste o surveys/ parlare con comunità con barriere accesso al digital banking;

Alternativamente abbiamo:
- Approcciato il problema da un POV più generale;
- Parlato con persone intorno a noi che utilizzano strumenti di digital banking;
- Identificato painpoints e touchpoint della loro customer journey;

La nostra ricerca ha identificato inizialmente come utenti, persone come i nostri genitori, i qualli a volte hanno delle problematiche d’utilizzo dell’applicazioni di bankin.
Da qui abbiamo cercato di capire meglio chi fossero i nostri utendi e abbiamo definito un utenza non necessariamente di gente adulta o anziana, ma anche di giovani che hanno poca dimestichezza con la tetcnologia e le operazioni bancarie.
Una volta capita la nostra utenza abbiamo sviluppato una persona (utente tipo) e di seguito riportiamo la Customer Journey Map utilizzata per capire meglio i suoi problemi, necessità e dubbi riguardo il percorso che affronta quando a contatto con l'app.

#### **Customer Journey map:**

<img width="1258" alt="Team6 - Customer Journey Map_Basic Journey_first time user 1" src="https://github.com/Haislich/Hack-to-innovate_team6/assets/145855979/8ed8d8a3-bc96-4f27-98f9-4b62ed2bfa7e">

Da qui abbiamo estrapolato tre principali painpoints:
- Difficoltà d’uso delle tecnologie 
- Poco interesse nella tecnologia
- Necessità di supporto nella navigazione

Abbiamo quindi specificato i passi successivi:
- WHAT: Semplificare l’accesso alle operazioni effettuabili in-app in totale autonomia;
- HOW: Tramite una barra di ricerca intelligente e una spiegazione step-by-step di come si effetuano le operazioni;
- WHO: Per quei utenti non sanno come utilizzare l’app o hanno necessità di supporto;



   

Per lo sviluppo della feature abbiamo prima di tutto analizzato lo stato dell'arte dell'applicazione e di applicazioni di banking simili. Analizzando l'alberatura attuale dell'app abbiamo cercato di capire come inserire la nostra implementazione. La funzione *"Hai bisogno di una mano”*  contiene ora in se i tre menu attuali di AIUTO-CERCA- PARLA CON NOI.

![Group 15](https://github.com/Haislich/Hack-to-innovate_team6/assets/145855979/e8e92218-cc19-414e-ab9a-6ec46f4e631c)




 
Capita la struttura dell'architettura dell'app, siamo passati alla prototipazione wireframe lo-fi delle schermate.
![Group 14](https://github.com/Haislich/Hack-to-innovate_team6/assets/145855979/31d2b873-a453-4699-b251-5464918ca959)




 
Quando la struttura generale ci è sembrata convincente, abbiamo continuato la prototipazione hi-fi. Per fare questo, abbiamo chiaramente mantenuto la UI dell'applicazione attuale e implementato la modalità assistita per gli utenti. Abbiamo seguito le specifiche del brand e il design system attuale per rendere il prototipo il più realistco possibile.
Nel [file Figma a cui si ha accesso]([https://www.figma.com/file/PbWAJc88VYP9eUOVKwBkhn/Team-6-Hackathon?type=design&node-id=0%3A1&mode=design&t=iPfJCv2T3ev1n4Ih-1](https://www.figma.com/proto/PbWAJc88VYP9eUOVKwBkhn/Team-6-Hackathon?page-id=1%3A2&type=design&node-id=1-67&viewport=532%2C364%2C0.09&t=z7NDR9yp63H9OjQ7-1&scaling=scale-down&mode=design)), si può vedere la modalità con cui è possibile effettuare un'operazione esemplificativa. In questo caso l'opearazione è una ricarica telefonica.




![gif1](https://github.com/Haislich/Hack-to-innovate_team6/assets/145855979/58ec27f6-8117-4a0d-8e72-468fb405a0a8)![gif3](https://github.com/Haislich/Hack-to-innovate_team6/assets/145855979/3e6d44a1-eaf0-4d6a-af2a-64cf560adc8d)![gif4](https://github.com/Haislich/Hack-to-innovate_team6/assets/145855979/c73e0f6d-0bb6-41bc-821e-d964db782c16)![gif5](https://github.com/Haislich/Hack-to-innovate_team6/assets/145855979/8277e8b0-4d7f-4610-b189-113a49190422)


   





## "Hai bisogno di una mano?": approccio tecnico
In questo readme vengono affrontate in breve le motivazioni tecniche che hanno portato alla scelta di un framework RAG.

L'incremento delle capacità computazionali a nostra disposizione ha permesso di dare il via a una nuova era di digitalizzazione.

L'avanzamento della digitalizzazione, se da un lato semplifica le operazioni per alcuni, le rende più complicate per altri. Vista l'adozione pressoché unanime di sistemi digitali, si richiede agli utenti finali uno sforzo sempre maggiore in termini di apprendimento.

Tuttavia, non tutti gli utenti hanno le capacità, il tempo o i mezzi per imparare a utilizzare una nuova app per ogni cosa, e tendono quindi a richiedere aiuto a persone con più esperienza.

Nei casi peggiori, o nei casi in cui non ci sia nessuno disponibile, gli utenti sono scoraggiati ad utilizzare l'applicativo poichè trovano l'esecuzione del task troppo difficile.

Questa strategia di "abbandono" non è sempre eseguibile; infatti, alcuni compiti possono essere eseguiti solo tramite l'applicativo. È importante, quindi, emancipare questa tipologia di utenti e dar loro la possibilità di fruire di servizi inclusivi senza dover aspettare un intervento esterno. Per fare ciò possiamo e dobbiamo utilizzare le innovazioni tecnologiche a nostra disposizione.

Le nuove svolte tecnologiche nell'ambito dell'intelligenza artificiale ci consentono di sostituire, almeno per compiti più basilari, l'ausilio di persone esterne. I Large Language Models (LLM) sono di particolare interesse in questo contesto.

## Large Language Models

I Large Language Models (LLM) sono modelli di Deep Learning progettati per comprendere e generalizzare il linguaggio umano. La loro utilità principale risiede nella loro capacità di elaborare il linguaggio e generare testi in modo avanzato. In particolare, questi modelli sono adatti per simulare una conversazione umana in cui un utente, magari incapace di completare un compito da solo, interagisce con un sistema di ChatBot per portare a termine il compito.

Ci sono alcune considerazioni importanti da tenere a mente quando si utilizzano questi modelli:

- **Ampia Quantità di Dati**: L'addestramento di questi modelli richiede una grande quantità di dati, non tutti attinenti al nostro dominio. Limitare il set di dati solo ai dati strettamente necessari potrebbe avere un effetto negativo, poiché il modello potrebbe diventare meno accurato.

- **Output Probabilistico**: Gli output generati da questi modelli sono basati su probabilità, e la risposta del modello potrebbe non sempre essere coerente con la richiesta dell'utente o con il contesto specifico. Questa tendenza a produrre risposte incoerenti o irrazionali è conosciuta come "allucinazione".

L'obiettivo desiderato è far sì che il ChatBot risponda in modo coerente al contesto specifico, ad esempio, nel nostro caso che agisca come ChatBot di "Intesa Sanpaolo". L'idea è di "allenare" il modello a comprendere e utilizzare termini e pattern specifici che potrebbero non essere pienamente rappresentati in un dataset di addestramento troppo ampio.

Tuttavia, al momento dell'addestramento del modello, molte delle conoscenze necessarie potrebbero non essere state acquisite. Di conseguenza, per affrontare tali problematiche, raccomandiamo di adottare un approccio ibrido. Questo approccio combina un framework RAG per fornire al modello informazioni aggiuntive al di fuori del set di addestramento e specifiche dell'applicazione. Se necessario, potrebbe essere opportuno eseguire un fine-tuning per acquisire conoscenze specifiche del settore.

Il framework RAG presenta numerosi vantaggi. In particolare, offre un'interpretabilità dell'output, permettendo di capire quale risorsa ha generato la risposta. Inoltre, è altamente adattabile a nuovi dati, riduce al minimo le allucinazioni e richiede un basso costo in termini di risorse e dati di addestramento.

Il contesto fornito al modello tramite il framework RAG potrebbe però non essere sempre sufficiente. Questo può verificarsi, ad esempio, quando manca un vocabolario adeguato. In questi casi, potrebbe essere necessario eseguire un ulteriore fine-tuning per ottenere l'output desiderato.

Il fine-tuning presenta diversi vantaggi, come una maggiore robustezza rispetto a casi limite e la capacità di operare in modo coerente in scenari specifici associati al dominio di interesse.
A differenza del framework RAG, il fine-tuning richiede una notevole quantità di risorse computazionali, dati aggiuntivi, tempo e hardware specializzato.
Il suo impiego dovrebbe essere limitato al caso in cui il solo framwork RAG non dia i risultati sperati.

In generale combinando entrambi gli approcci, è possibile sviluppare un modello con un linguaggio specializzato, robusto nei confronti dei casi limite e facilmente adattabile al contesto.



## References

### Inclusione digitale

[Inclusive digital innovation](https://open.gov.it/governo-aperto/innovazione-digitale-inclusiva)

[Digital inclusion](https://digital-strategy.ec.europa.eu/en/policies/digital-inclusion)


[What is digital inclusion ?](https://www.beconnectednetwork.org.au/news-events/what-digital-inclusion)

### Accessibilità

[A Designer’s Guide to Documenting Accessibility & User Interactions](https://stephaniewalter.design/blog/a-designers-guide-to-documenting-accessibility-user-interactions/#kit)

[Accessible but never boring (Part 2)](https://medium.com/transferwise-design/accessible-but-never-boring-part-2-e188db299bd0)

[We’re missing the primary point of designing for accessibility](https://medium.com/design-bootcamp/were-missing-the-primary-point-of-designing-for-accessibility-421e4239ecee)

[What Are Accessibility Overlays?](https://briefs.video/videos/what-are-accessibility-overlays/)

[Web Accessibility in mind contrast checker](https://webaim.org/resources/contrastchecker/)

[Eight shapes](https://eightshapes.com/)

[Criteri di accessibilità](https://drive.google.com/file/d/13wFL77TLSJzJfc3V06M2iQPesrZFrl3W/view)

[Intesa Sanpaolo accessible by design: dal design system all’assessment](https://www.youtube.com/watch?v=1LDWTCi1Axg)

[Accessibility tutorial](https://www.w3schools.com/accessibility/)

[Web Content Accessibility Guidelines (WCAG) 2.1](https://www.w3.org/Translations/WCAG21-it/)

### RAG AI & Generative AI

[What are Generative AI models?](https://youtu.be/hfIUstzHs9A?si=hYsnIk68cnSOx7xg)

[LLM Embeddings](https://www.youtube.com/watch?v=X5DZL58mBg0)

[LLM Embeddings explained simply](https://llm.datasette.io/en/stable/embeddings/index.html)

[Contexts in LLM](https://medium.com/@simon_attard/giving-large-language-models-context-2d1956a6a017)

[Example of context in Github Copilot](https://twitter.com/marvinvonhagen/status/1657060506371346432?lang=en)

[RAG for LLMs](https://www.hopsworks.ai/dictionary/retrieval-augmented-generation-llm#:~:text=Retrieval%2Daugmented%20generation%20(RAG),%2C%20and%20recent%2Frelevant%20knowledge.)
[Hallucinations in LLMs](https://masterofcode.com/blog/hallucinations-in-llms-what-you-need-to-know-before-integration#:~:text=Hallucination%20in%20LLMs%20refers%20to,for%20organizations%20utilizing%20these%20models.)

[Full Fine-Tuning, PEFT, Prompt Engineering, and RAG: Which One Is Right for You?](https://deci.ai/blog/fine-tuning-peft-prompt-engineering-and-rag-which-one-is-right-for-you/#:~:text=Fine%2Dtuning%20can%20be%20used,is%20the%20way%20to%20go.)

[What is retrieval-augmented generation?](https://research.ibm.com/blog/retrieval-augmented-generation-RAG)

[How to customize LLMs like ChatGPT with your own data and documents](https://bdtechtalks.com/2023/05/01/customize-chatgpt-llm-embeddings/)

[Master Prompt Engineering: LLM Embedding and fine-tuning](https://www.promptengineering.org/master-prompt-engineering-llm-embedding-and-fine-tuning/)

[Things I'm learning while training SuperHot](https://kaiokendev.github.io/til)

[Demystifying embeddings 101](https://datasciencedojo.com/blog/embeddings-and-llm/)

[Large Language Model - Wikipedia](https://en.wikipedia.org/wiki/Large_language_model)

[What is a chatbot](https://www.ibm.com/topics/chatbots)

[GPT best practices - OpenAi](https://platform.openai.com/docs/guides/gpt-best-practices)

### Altro

[Le funzionalità dell'app | App Intesa Sanpaolo Mobile](https://www.youtube.com/watch?v=oLiY1nHtux8)

[INTESA SANPAOLO: ISP MOBILE OVERALL DIGITAL EXPERIENCE LEADER IN THE EMEA AREA](https://www.reply.com/iriscube-reply/en/reply-intesa-sanpaolo-isp-mobile-overall-digital-experience-leader-area-emea)

[Ricarica cellulare | App Intesa Sanpaolo Mobile](https://www.youtube.com/watch?v=FbGAccz4b7M)

[Elderly users and their main challenges usability with mobile applications: a systematic review](https://link.springer.com/chapter/10.1007/978-3-030-23570-3_31)
