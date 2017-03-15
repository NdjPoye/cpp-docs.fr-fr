---
title: "Solutions de remplacement de l&#39;architecture document/vue | Microsoft Docs"
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
  - "CDocument (classe), espace requis"
  - "documents, applications sans"
  - "vues, applications sans"
ms.assetid: 2c22f352-a137-45ce-9971-c142173496fb
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Solutions de remplacement de l&#39;architecture document/vue
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les applications de MFC utilisent généralement l'architecture documents\/Vue pour gérer les informations, les formats de fichier, et la représentation visuelle des données à des utilisateurs.  Pour la majorité des applications bureautiques, l'architecture documents\/Vue est une architecture appropriée et efficace d'application.  Cette architecture sépare les données de visualisation et, dans la plupart des cas, simplifie votre application et réduit le code redondant.  
  
 Toutefois, l'architecture documents\/Vue n'est pas appropriée pour certains cas.  Prenons les exemples de :  
  
-   Si vous déplacez une application écrite dans l'Assistant de C pour Windows, vous pouvez avoir envie de compléter votre port avant d'ajouter la prise en charge de documents\/vue dans votre application.  
  
-   Si vous entrez un utilitaire léger, vous pouvez constater que vous pouvez l'effectuer sans l'architecture de documents\/Vue.  
  
-   Si votre code d'origine combine déjà la gestion des données et l'affichage de données, porter du code du document ou de vue ne vaut pas l'effort car vous devez distinguer les deux.  Vous pouvez préférer de laisser le code tel qu'il est.  
  
 Pour créer une application qui n'utilise pas l'architecture de documents\/Vue, désactivez la case à cocher de **Prise en charge de l'architecture Document\/Vue** lors de l'étape 1 de l'Assistant d'Application MFC.  Pour plus d'informations, consultez [Assistant d'Application MFC](../mfc/reference/mfc-application-wizard.md) .  
  
> [!NOTE]
>  Les applications basées sur les boîtes de dialogue produits par l'Application MFC n'utilisent pas l'architecture documents\/Vue, donc la case à cocher de **Prise en charge de l'architecture Document\/Vue** est désactivée si vous sélectionnez le type d'application de dialogue.  
  
 Les assistants Visual C\+\+, ainsi que les éditeurs de boîtes de dialogue, travaillent avec l'application générée comme ils le feraient avec n'importe quelle autre application générée par l'Assistant.  L'application peut prendre en charge des barres d'outils, les barres de défilement, et la barre d'état, et a une zone **À propos de**.  Votre application n'enregistre aucun modèle de document et ne contient pas une classe de document.  
  
 Notez que votre application générée possède une classe d'affichage, **CChildView**, dérivée d' `CWnd`.  MFC crée et place une instance de la classe d'affichage dans les cadres des fenêtres créées par votre application.  MFC impose toujours à l'aide d'une vue de fenêtre, car elle simplifie la position et la gestion du contenu de l'application.  Vous pouvez ajouter du code de peinture au membre d' `OnPaint` de cette classe.  Votre code doit ajouter des barres de défilement à la vue plutôt qu'au cadre.  
  
 Étant donné que l'architecture documents\/Vue fournie par MFC est chargée d'implémenter plusieurs fonctionnalités de base d'une application, l'absence de votre projet signifie que vous êtes chargé d'implémenter plusieurs fonctionnalités importantes de votre application:  
  
-   Comme fourni par l'Assistant d'Application MFC, le menu pour votre application contient uniquement les commandes `New` et `Exit` dans le menu de **Fichier**. \(La commande de `New` n'est prise en charge que pour les applications MDI, et non pas pour des applications de SDI sans prise en charge de documents\/vue.\) La ressource du menu générée ne prend pas en charge une liste \(derniers fichiers utilisés\) de MRU.  
  
-   Vous devez ajouter des fonctions et des implémentations de gestion pour toutes les commandes que votre application prend en charge, notamment **Ouvrir** et **Enregistrer** dans le menu de **Fichier**.  MFC fournit normalement du code pour prendre en charge ces fonctionnalités, mais cette prise en charge est étroitement liée à l'architecture documents\/Vue.  
  
-   La barre d'outils pour votre application, si vous en avez demandé une, est minimale.  
  
 Il est fortement recommandé d'utiliser l'Assistant d'Application MFC pour créer des applications sans architecture documents\/Vue, car il garantit une architecture correcte de MFC.  Toutefois, si vous devez éviter d'utiliser l'Assistant, voici plusieurs approches pour ignorer l'architecture documents\/Vue dans votre code:  
  
-   Traitez le document comme une annexe inutilisée et implémentez le code de gestion des données de la classe d'affichage, comme suggéré précédemment.  La surcharge du document est relativement basse.  Un objet seul d' [CDocument](../mfc/reference/cdocument-class.md) subit une petite quantité de charge par lui\-même, plus la surcharge de classes de base, d' [CCmdTarget](../mfc/reference/ccmdtarget-class.md) et d' [CObject](../mfc/reference/cobject-class.md)de **CDocument**.  Les deux dernières classes sont petites.  
  
     Déclaré dans **CDocument**:  
  
    -   Deux objets d' `CString`.  
  
    -   Trois **BOOL**S.  
  
    -   Un pointeur d' `CDocTemplate`.  
  
    -   Un objet d' `CPtrList`, qui contient une liste des vues du document.  
  
     En outre, le document requiert la durée nécessaire pour créer l'objet de document, ses objets de vue, un cadre de fenêtre et un objet modèle de document.  
  
-   Traitez à la fois le document et la vue comme des annexes inutilisées.  Mettez votre code de gestion des données et de dessin dans le cadre de la fenêtre plutôt que dans la vue.  Cette approche est plus proche du modèle de programmation du langage C.  
  
-   Remplacez les parties de l'infrastructure MFC qui créent le document et la vue pour éliminer les créer du tout.  Le processus de création de documents commence par un appel à `CWinApp::AddDocTemplate`.  Éliminez l'appel de la fonction membre d' `InitInstance` de la classe d'application et, au lieu de cela, créez une fenêtre cadre d' `InitInstance` vous\-même.  Mettez votre code de gestion des données dans votre cadre de fenêtre de la classe.  Le processus de création de documents\/vue est illustré dans [Document de création\/vue](../mfc/document-view-creation.md).  Il s'agit de plus de travail et requiert une connaissance plus profonde de l'infrastructure, mais vous libère entièrement de la surcharge de documents\/vue.  
  
 L'article [MFC: En utilisant des classes de base de données sans documents et vues](../data/mfc-using-database-classes-without-documents-and-views.md) fournit des exemples plus concrets des méthodes de documents\/vue dans le contexte des applications de base de données.  
  
## Voir aussi  
 [Architecture document\/vue](../mfc/document-view-architecture.md)