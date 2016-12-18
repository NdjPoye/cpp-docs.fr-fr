---
title: "Contextes de p&#233;riph&#233;rique | Microsoft Docs"
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
  - "BeginPaint (méthode), CPaintDC"
  - "CClientDC (classe), et méthode GetDC"
  - "CClientDC (classe), et méthode ReleaseDC"
  - "CDC (classe), objets"
  - "zones clientes"
  - "zones clientes, et contexte de périphérique"
  - "CMetaFileDC (classe), et méthode OnPrepareDC"
  - "CPaintDC (classe), contexte de périphérique pour la peinture"
  - "contextes de périphérique (C++)"
  - "contextes de périphérique (C++), à propos des contextes de périphérique"
  - "contextes de périphérique (C++), CDC (classe)"
  - "dessin indépendant du périphérique"
  - "dessiner, contexte de périphérique"
  - "dessiner, directement dans les fenêtres"
  - "dessiner, dans les contextes de périphérique et souris"
  - "EndPaint (méthode)"
  - "fenêtres frame (C++), contextes de périphérique"
  - "objets GDI (C++), contextes de périphérique"
  - "GetDC (méthode) et classe CClientDC"
  - "objets graphiques, contextes de périphérique"
  - "métafichiers et contextes de périphérique"
  - "souris (C++), dessin et contextes de périphérique"
  - "OnPrepareDC (méthode)"
  - "peinture et contexte de périphérique"
  - "imprimantes (C++), contextes de périphérique"
  - "ReleaseDC (méthode)"
  - "interface utilisateur (C++), contextes de périphérique"
  - "fenêtres (C++), et contexte de périphérique"
  - "fenêtres (C++), dessiner directement dans"
ms.assetid: d0cd51f1-f778-4c7e-bf50-d738d10433c7
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Contextes de p&#233;riph&#233;rique
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un contexte de périphérique est une structure de données windows qui contient des informations sur les attributs de dessin d'un périphérique tels qu'une vue ou une imprimante.  Tous les appels de dessin sont effectuées via un objet contexte de périphérique, qui encapsule les API Windows pour ajouter des lignes, des formes, et texte.  Les contextes de périphérique permettent des dessin indépendants du périphérique dans Windows.  Les contextes de périphérique peuvent être utilisés pour dessiner à l'écran, à l'imprimante, ou à un métafichier.  
  
 les objets [CPaintDC](../mfc/reference/cpaintdc-class.md) encapsulent l'idiome commun Windows, appelant ainsi la fonction `BeginPaint`, puis dessinant dans le contexte de périphérique, puis appelant la fonction `EndPaint`.  Le constructeur d' `CPaintDC` appelle `BeginPaint` pour vous, et le destructeur appelle `EndPaint`.  Le processus simplifié est de créer l'objet [CDC](../mfc/reference/cdc-class.md), le dessiner, puis détruit l'objet `CDC`.  Dans l'infrastructure, une grande partie de ce processus est automatisée.  En particulier, votre fonction d' `OnDraw` est passée `CPaintDC` déjà préparé \(via `OnPrepareDC`\), et vous dessinez simplement dans celle\-ci.  Il est détruit par l'infrastructure et le contexte sous\-jacent de périphérique est libéré vers windows sur le retour de l'appel à la fonction d' `OnDraw`.  
  
 les objets [CClientDC](../mfc/reference/cclientdc-class.md) encapsulent et utilisent un contexte du périphérique qui représente uniquement la zone client d'une fenêtre.  Le constructeur `CClientDC` appelle la fonction `GetDC`, et les destructeurs appellent la fonction `ReleaseDC`.  les objets [CWindowDC](../mfc/reference/cwindowdc-class.md) encapsulent un contexte du périphérique qui représente la fenêtre entière, y compris son cadre.  
  
 les objets [CMetaFileDC](../mfc/reference/cmetafiledc-class.md) encapsulent le dessin dans un métafichier Windows.  Contrairement à `CPaintDC` passé à `OnDraw`, vous devez dans ce cas appeler [OnPrepareDC](../Topic/CView::OnPrepareDC.md) vous\-même.  
  
## Dessin à la souris  
 La plupart des dessins dans un programme de mise en page — et donc la plupart des travaux de contexte de périphérique — s'effectue dans la fonction membre de la vue de `OnDraw`.  Toutefois, vous pouvez encore utiliser des objets contexte de périphérique à d'autres fins.  Par exemple, pour fournir des commentaires de suivi pour le mouvement de la souris dans une vue, vous devez dessiner directement dans la vue sans attendre que `OnDraw` soit appelé.  
  
 Dans ce cas, vous pouvez utiliser un objet contexte de périphérique d' [CClientDC](../mfc/reference/cclientdc-class.md) pour ajouter directement dans la vue.  
  
### Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [\<caps:sentence id\="tgt22" sentenceid\="a12b51e88715aef1e34dc9b8f4447117" class\="tgtSentence"\>Outil de contextualisation \(définition\)\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/dd183553)  
  
-   [Dessin dans une vue](../mfc/drawing-in-a-view.md)  
  
-   [Interprétation de l'entrée utilisateur via une vue](../mfc/interpreting-user-input-through-a-view.md)  
  
-   [\<caps:sentence id\="tgt25" sentenceid\="f3dbb554cb14503827bf0ebda53953d7" class\="tgtSentence"\>Lignes droites et lignes courbées\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/dd145028)  
  
-   [\<caps:sentence id\="tgt26" sentenceid\="365f749101c5eabc8b3be48de1dc3d6b" class\="tgtSentence"\>formes remplies\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/dd162714)  
  
-   [\<caps:sentence id\="tgt27" sentenceid\="dc86a6302992c2d9f64d0fc6a8cfef75" class\="tgtSentence"\>polices de caractères et texte\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/dd144819)  
  
-   [\<caps:sentence id\="tgt28" sentenceid\="62848e3ce5804aa985513a7922ff87b2" class\="tgtSentence"\>Couleurs\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/dd183450)  
  
-   [\<caps:sentence id\="tgt29" sentenceid\="ee85800dfcba9a5bdf11f101e1bbadeb" class\="tgtSentence"\>Transformations et systèmes de coordonnées\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/dd183475)  
  
## Voir aussi  
 [Objets fenêtres](../mfc/window-objects.md)