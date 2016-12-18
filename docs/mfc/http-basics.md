---
title: "&#201;l&#233;ments fondamentaux relatifs &#224; HTTP | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Requêtes HTTP, codes de retour"
  - "HTTP, codes de retour"
  - "codes de retour"
ms.assetid: 5b7421bf-42c8-4f3a-8566-8ff5957f58cc
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# &#201;l&#233;ments fondamentaux relatifs &#224; HTTP
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lorsque vous écrivez une application internet, souvent vous examinez et ajouter aux informations de l'en\-tête HTTP.  Les codes renvoyés indiquent la réussite ou l'échec de l'événement demandé.  Plusieurs codes de retour courants sont répertoriés dans le tableau suivant.  
  
|Code de retour|Signification|  
|--------------------|-------------------|  
|200|L'URL localisée, par exemple|  
|400|Demande inintelligible|  
|404|URL demandée non trouvée|  
|405|Le serveur ne prend pas en charge la méthode demandée|  
|500|Erreur inconnue du serveur|  
|503|Service non disponible|  
  
 Les réponse HTTP sont groupées comme elles sont montrées dans le tableau suivant.  
  
|Group|Signification|  
|-----------|-------------------|  
|200–299|Opération réussie|  
|300–399|Information|  
|400–499|Erreur de requête|  
|500–599|Erreur de serveur|  
  
 Le protocole HTTP \(hypertext transfer protocol\) est un protocole au niveau de l'application pour les systèmes d'informations d'hypermédia.  Pour plus d'informations sur HTTP, et comment les navigateurs Web et le serveur communiquent, consultez la spécification du protocole HTTP \(hypertext transfer protocol\) :  
  
 [http:\/\/www.w3.org\/pub\/WWW\/Protocols\/](http://www.w3.org/pub/WWW/Protocols/)  
  
## Voir aussi  
 [Éléments fondamentaux relatifs à la programmation Internet MFC](../mfc/mfc-internet-programming-basics.md)