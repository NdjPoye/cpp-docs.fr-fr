---
title: "&#201;change de donn&#233;es de bo&#238;tes de dialogue | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "annuler un échange de données"
  - "capturer l'entrée d'utilisateur"
  - "CDataExchange (classe), utiliser DDX"
  - "DDX (échange de données de boîtes de dialogue), annuler"
  - "DDX (échange de données de boîtes de dialogue), mécanisme d'échange de données"
  - "données de boîte de dialogue"
  - "données de boîte de dialogue, récupérer"
  - "boîtes de dialogue, échange de données"
  - "boîtes de dialogue, initialiser"
  - "boîtes de dialogue, récupérer l'entrée d'utilisateur via DDX"
  - "DoDataExchange (méthode)"
  - "initialiser des boîtes de dialogue"
  - "récupérer les données d'une boîte de dialogue"
  - "transférer les données d'une boîte de dialogue"
  - "UpdateData (méthode)"
  - "entrée d'utilisateur, récupérer à partir de boîtes de dialogues MFC"
ms.assetid: 4675f63b-41d2-45ed-b6c3-235ad8ab924b
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# &#201;change de donn&#233;es de bo&#238;tes de dialogue
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Si vous utilisez le mécanisme DDX, vous définissez les valeurs initiales des attributs de l'objet dialog, en général dans le gestionnaire de `OnInitDialog` ou le constructeur de dialogue.  Juste avant que le dialogue ne s'affiche, le mécanisme DDX de l'infrastructure transfère les valeurs des attributs aux contrôles dans la boîte de dialogue, où elles apparaissent lorsque la boîte de dialogue s'affiche en réponse à `DoModal` ou à **Create**.  L'implémentation par défaut de `OnInitDialog` dans `CDialog` appelle la méthode `UpdateData` de la classe `CWnd` pour initialiser les contrôles dans la boîte de dialogue.  
  
 Le même mécanisme transfère les valeurs des contrôles dans les attributs lorsque l'utilisateur clique sur le bouton OK \(ou lorsque vous appelez la méthode `UpdateData` avec l'argument **TRUE**\).  Le mécanisme de validation des données de dialogue valide tous les éléments de données pour lesquels vous avez spécifié les règles de validation.  
  
 L'illustration suivante montre l'échange de données de dialogue.  
  
 ![Échange de données de la boîte de dialogue](../mfc/media/vc379d1.png "vc379D1")  
Échange de données de boîte de dialogue  
  
 `UpdateData` fonctionne dans les deux sens, comme spécifié par le paramètre **BOOL** passé à celui\-ci.  Pour effectuer l'échange, `UpdateData` génère un objet `CDataExchange` et appelle la méthode `DoDataExchange` de la substitution de votre classe de dialogue `CDialog`.  `DoDataExchange` accepte un argument du type `CDataExchange`.  L'objet `CDataExchange` passé à `UpdateData` représente le contexte de l'échange, et définit des informations telles que la direction de l'échange.  
  
 Lorsque vous \(ou un Assistant Code\) remplace `DoDataExchange`, vous spécifiez un appel à une fonction DDX par membre de données \(contrôle\).  Chaque fonction DDX sait échanger des données dans les deux directions selon le contexte fourni par l'argument `CDataExchange` passé à votre `DoDataExchange` par `UpdateData`.  
  
 MFC fournit de nombreuses fonctions DDX pour différents types d'échange.  L'exemple suivant illustre la substitution de `DoDataExchange` dans laquelle deux fonctions DDX et une fonction DDV sont appelées :  
  
 [!code-cpp[NVC_MFCControlLadenDialog#49](../mfc/codesnippet/CPP/dialog-data-exchange_1.cpp)]  
  
 Les lignes de `DDX_` et `DDV_` sont une table de données.  Les fonctions d'exemple de DDX et DDV sont affichées pour un contrôle case et un contrôle de zone d'édition, respectivement.  
  
 Si l'utilisateur annule une boîte de dialogue modale, la méthode `OnCancel` ferme la boîte de dialogue et `DoModal` retourne la valeur **IDCANCEL**.  Dans ce cas, aucune donnée n'est échangée entre la boîte de dialogue et l'objet du dialogue.  
  
## Voir aussi  
 [Échange et validation de données de boîtes de dialogue](../mfc/dialog-data-exchange-and-validation.md)   
 [Cycle de vie d'une boîte de dialogue](../mfc/life-cycle-of-a-dialog-box.md)   
 [Validation de données de boîtes de dialogue](../mfc/dialog-data-validation.md)