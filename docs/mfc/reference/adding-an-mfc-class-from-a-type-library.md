---
title: "Ajout d&#39;une classe MFC &#224; partir d&#39;une biblioth&#232;que de types | Microsoft Docs"
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
  - "classes (C++), ajouter MFC"
  - "MFC, ajouter des classes à partir de bibliothèques de types"
  - "bibliothèques de types, ajouter des classes MFC à partir de"
ms.assetid: aba40476-3cfb-47af-990e-ae2e9e0d79cf
caps.latest.revision: 13
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Ajout d&#39;une classe MFC &#224; partir d&#39;une biblioth&#232;que de types
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Utilisez cet Assistant pour créer une classe MFC à partir d'une interface dans une bibliothèque de types disponible.  Vous pouvez ajouter une classe MFC à une [application MFC](../../mfc/reference/creating-an-mfc-application.md), à une [DLL MFC](../../mfc/reference/creating-an-mfc-dll-project.md) ou à un [contrôle ActiveX MFC](../../mfc/reference/creating-an-mfc-activex-control.md).  
  
> [!NOTE]
>  Vous n'êtes pas tenu de créer de projet MFC avec Automation activé pour ajouter une classe à partir d'une bibliothèque de types.  
  
 Une bibliothèque de types contient une description binaire des interfaces exposées par un composant, en définissant les méthodes ainsi que leurs paramètres et leurs types de retour.  Votre bibliothèque de types doit être inscrite pour s'afficher dans la liste **Bibliothèques de types disponibles** de l'Assistant Ajout de classes d'une Typelib.  Pour plus d'informations, consultez « Inside Distributed COM: Type Libraries and Language Integration » dans MSDN Library.  
  
### Pour ajouter une classe MFC à partir d'une bibliothèque de types  
  
1.  Dans l'**Explorateur de solutions** ou dans l'[Affichage de classes](http://msdn.microsoft.com/fr-fr/8d7430a9-3e33-454c-a9e1-a85e3d2db925), cliquez avec le bouton droit sur le nom du projet auquel vous souhaitez ajouter la classe.  
  
2.  Dans le menu contextuel, cliquez sur **Ajouter**, puis sur **Ajouter une classe**.  
  
3.  Dans le volet Modèles de la boîte de dialogue [Ajouter une classe](../../ide/add-class-dialog-box.md), cliquez sur **Classe MFC à partir d'une TypeLib**, puis sur **Ouvrir** pour afficher [Assistant Ajout de classes d'une Typelib](../../mfc/reference/add-class-from-typelib-wizard.md).  
  
 Dans l'Assistant, vous pouvez ajouter plusieurs classes dans une bibliothèque de types.  De même, vous pouvez ajouter des classes à partir de plusieurs bibliothèques de types dans une session d'Assistant unique.  
  
 L'Assistant crée une classe MFC, dérivée de [COleDispatchDriver](../../mfc/reference/coledispatchdriver-class.md), pour chaque interface ajoutée à partir de la bibliothèque de types sélectionnée.  `COleDispatchDriver` implémente le côté client d'OLE automation.  
  
## Voir aussi  
 [Clients Automation](../../mfc/automation-clients.md)   
 [Clients Automation : utilisation des bibliothèques de types](../../mfc/automation-clients-using-type-libraries.md)