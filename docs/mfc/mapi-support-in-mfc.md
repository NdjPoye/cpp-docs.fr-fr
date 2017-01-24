---
title: "Prise en charge MAPI dans MFC | Microsoft Docs"
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
  - "CDocument (classe), et MAPI"
  - "prise en charge MAPI dans les MFC"
  - "MAPI, MFC"
  - "MFC, prise en charge MAPI"
  - "OnFileSendMail (méthode)"
  - "OnUpdateFileSendMail (méthode)"
ms.assetid: cafbecb1-0427-4077-b4b8-159bae5b49b8
caps.latest.revision: 12
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Prise en charge MAPI dans MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les ressources MFC prennent en charge un sous\-ensemble de l'interface de programmation d'applications \(MAPI\) de messagerie Microsoft dans la classe **CDocument**.  En particulier, **CDocument** contient les fonctions membres qui déterminent si la prise en charge des messages électroniques est présente sur l'ordinateur de l'utilisateur et, si tel est le cas, présente une commande Envoyer un Message dont l'ID de commande standard est **ID\_FILE\_SEND\_MAIL**.  La fonction gestionnaire de MFC de cette commande permet à l'utilisateur envoyer un document via la messagerie électronique.  
  
> [!TIP]
>  Bien que MFC n'inclut pas l'intégralité de la fonction MAPI, vous pouvez toujours appeler des fonctions MAPI directement, de la même manière que vous appelleriez des fonctions API Win32 directement des programmes MFC.  
  
 Créer la commande Envoyer un Message dans votre application est très simple.  MFC fournit une implémentation pour empaqueter un document \(ceci étant, **CDocument**\- objet dérivé\) comme pièce jointe et l'envoyer en tant que message.  La pièce jointe est équivalente à une commande de sauvegarde du fichier qui stocke \(sérialise\) le contenu du document dans le message électronique.  Cette implémentation demande au client de messagerie sur l'ordinateur de l'utilisateur de permettre à l'utilisateur la possibilité d'adresser le message et d'ajouter le sujet et le texte au message électronique.  Les utilisateurs voient l'interface usuelle de l'application de messagerie.  Cette fonctionnalité est fournie par deux fonctions membres **CDocument**: `OnFileSendMail` et `OnUpdateFileSendMail`.  
  
 MAPI doit lire le fichier pour envoyer la pièce jointe.  Si l'application maintient le fichier de données ouvert pendant un appel de fonction `OnFileSendMail`, le fichier doit être ouvert avec un mode de partage qui permette à plusieurs processus d'accéder au fichier.  
  
> [!NOTE]
>  Une version remplaçante de `OnFileSendMail` de la classe `COleDocument` traite correctement les documents composés.  
  
#### Pour implémenter une commande Envoyer un Message avec MFC  
  
1.  Utilisez l'éditeur de menu de Visual C\+\+ pour ajouter un élément de menu dont l'ID de commande est **ID\_FILE\_SEND\_MAIL**.  
  
     Cet ID de commande est fournie par l'environnement dans AFXRES.H.  La commande peut être ajoutée à tout menu, mais elle est généralement ajoutée au menu de **Fichier**.  
  
2.  Ajoutez manuellement le code suivant à la table des messages de votre document :  
  
     [!code-cpp[NVC_MFCDocView#9](../mfc/codesnippet/CPP/mapi-support-in-mfc_1.cpp)]  
  
    > [!NOTE]
    >  Cette table des messages fonctionne pour un document dérivé de **CDocument** ou de **COleDocument** — elle prend la classe de base appropriée dans chacun des cas, même si la table des messages se trouve dans votre classe dérivée de document.  
  
3.  Générez votre application.  
  
 Si la prise en charge des messages est disponible, MFC active l'élément de menu avec `OnUpdateFileSendMail` et traite ensuite la commande avec `OnFileSendMail`.  Si la prise en charge des messages n'est pas disponible, MFC supprime automatiquement l'élément de menu afin que l'utilisateur ne le voit pas.  
  
> [!TIP]
>  Au lieu d'ajouter manuellement des entrées de la table des messages comme décrit précédemment, vous pouvez utiliser la fenêtre Propriétés de la classe pour mapper des messages aux fonctions.  Pour plus d'informations, consultez [Mappage de messages en fonctions](../mfc/reference/mapping-messages-to-functions.md).  
  
 Pour plus à ce sujet d'informations, consultez la vue d'ensemble [](../mfc/mapi.md "MAPI").  
  
 Pour plus d'informations sur les fonctions membres **CDocument** qui activent MAPI, consultez :  
  
-   [CDocument::OnFileSendMail](../Topic/CDocument::OnFileSendMail.md)  
  
-   [CDocument::OnUpdateFileSendMail](../Topic/CDocument::OnUpdateFileSendMail.md)  
  
-   [COleDocument::OnFileSendMail](../Topic/COleDocument::OnFileSendMail.md)  
  
## Voir aussi  
 [MAPI](../mfc/mapi.md)