---
title: "Cr&#233;ation d&#39;une application MFC bas&#233;e sur les formulaires | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.mfcforms.project"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "applications (MFC), basées sur les formulaires"
  - "applications basées sur les formulaires"
ms.assetid: 048d2f7d-b60d-4386-ad8e-71d49af9c05e
caps.latest.revision: 12
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Cr&#233;ation d&#39;une application MFC bas&#233;e sur les formulaires
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Un formulaire est une boîte de dialogue dotée de contrôles qui permettent à un utilisateur d'accéder à des données et de les modifier éventuellement.  Vous pouvez par exemple développer une application dans laquelle l'utilisateur effectue une sélection parmi plusieurs formulaires.  Une application basée sur les formulaires permet habituellement à l'utilisateur d'accéder à des formulaires en cliquant dans le menu **Fichier** sur **Nouveau**.  Une application basée sur des boîtes de dialogue, qui ne permet pas aux utilisateurs d'accéder à une option **Nouveau** dans le menu **Fichier**, est également considérée comme une application basée sur les formulaires.  
  
 Une application basée sur les formulaires dotée d'une interface monodocument \(SDI\) ne permet l'exécution que d'une seule instance d'un formulaire donné à la fois.  Il est possible d'exécuter différents formulaires en même temps à partir d'une application basée sur les formulaires dotée d'une interface SDI en sélectionnant un nouveau formulaire à partir de l'option **Nouveau** du menu **Fichier**.  
  
 Si vous créez une application basée sur les formulaires dotée d'une interface multidocument \(MDI\), l'application pourra prendre en charge plusieurs instances du même formulaire.  
  
 Si vous créez une application prenant en charge plusieurs documents de niveau supérieur, le bureau constitue le parent implicite du document et le frame du document ne se limite pas à la zone cliente de l'application.  Vous pouvez ouvrir plusieurs instances du document, chaque instance disposant de ses propres frame, menu et icône de barre des tâches.  Fermez de manière individuelle les instances suivantes des documents, mais si vous sélectionnez l'option `Exit` du menu **Fichier** de l'instance initiale, l'application ferme toutes les instances.  
  
 Les applications dotées d'une interface SDI, MDI et celles qui prennent en charge plusieurs documents de niveau supérieur sont toutes des applications basées sur les formulaires et utilisent l'architecture Document\/Vue.  
  
 Par définition, toute application basée sur des boîtes de dialogue est basée sur les formulaires.  Une application basée sur des boîtes de dialogue n'utilise pas l'architecture Document\/Vue ; vous devez donc gérer les méthodes de création et d'accès de vos formulaires supplémentaires.  
  
 La classe de base des applications basées sur les formulaires est [CFormView](../../mfc/reference/cformview-class.md).  Si votre application dispose d'une prise en charge des bases de données, vous pouvez également sélectionner n'importe quelle classe dérivée de `CFormView`.  Un formulaire correspond à n'importe quelle fenêtre dérivée de `CFormView` ou de n'importe quelle classe qui hérite de `CFormView`.  
  
 Même si vous utilisez une classe de base comme [CView](../../mfc/reference/cview-class.md), vous pouvez transformer ultérieurement vos applications en applications basées sur les formulaires en [ajoutant une classe MFC](../../mfc/reference/adding-an-mfc-class.md) dérivée de `CFormView` et en activant la case à cocher **Générer des ressources DocTemplate** dans l'[Assistant Classe MFC](../../mfc/reference/document-template-strings-mfc-add-class-wizard.md).  
  
 Une fois l'Assistant terminé, votre projet s'ouvre, et, si vous avez sélectionné `CFormView` \(ou une classe qui hérite de `CFormView`\) en tant que classe de base ou si vous avez créé une application basée sur des boîtes de dialogue, Visual C\+\+ ouvre l'Éditeur de boîtes de dialogue.  À ce stade, vous êtes prêt à concevoir votre premier formulaire.  
  
### Pour commencer à créer un exécutable MFC basé sur les formulaires  
  
1.  Suivez les instructions indiquées dans [Création d'une application MFC](../../mfc/reference/creating-an-mfc-application.md).  
  
2.  Dans la page [Type d'application](../../mfc/reference/application-type-mfc-application-wizard.md) de l'Assistant Application MFC, activez la case à cocher **Prise en charge de l'architecture Document\/Vue**.  
  
3.  Sélectionnez **Mono document \(SDI\)**, **Multidocument \(MDI\)** ou **Plusieurs documents de niveau supérieur**.  
  
    > [!NOTE]
    >  Si vous avez choisi une application dotée d'une interface SDI, MDI ou prenant en charge plusieurs documents de niveau supérieur, la classe `CView` est définie par défaut en tant que classe de base pour la vue de l'application dans la page [Classes générées](../../mfc/reference/generated-classes-mfc-application-wizard.md) de l'Assistant.  Pour créer une application basée sur les formulaires, vous devez sélectionner `CFormView` en tant que classe de base pour la vue de l'application.  Notez que l'Assistant ne fournit aucune prise en charge d'impression pour une application basée sur les formulaires.  
  
4.  Définissez les autres options du projet voulues dans les autres pages de l'Assistant.  
  
5.  Cliquez sur **Terminer** pour générer l'application squelette.  
  
 Pour plus d'informations, consultez :  
  
-   [Classes vues dérivées](../../mfc/derived-view-classes-available-in-mfc.md)  
  
-   [Solutions de remplacement de l'architecture document\/vue](../../mfc/alternatives-to-the-document-view-architecture.md)  
  
-   [Choix en matière de conception d'applications](../../mfc/application-design-choices.md)  
  
## Voir aussi  
 [Assistant Application MFC](../../mfc/reference/mfc-application-wizard.md)   
 [Mode Formulaire](../../mfc/form-views-mfc.md)   
 [Création d'une application MFC de style Explorateur de fichiers](../../mfc/reference/creating-a-file-explorer-style-mfc-application.md)   
 [Création d'une application MFC de style navigateur Web](../../mfc/reference/creating-a-web-browser-style-mfc-application.md)