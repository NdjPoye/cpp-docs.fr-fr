---
title: "Ajout d&#39;une classe &#224; partir d&#39;un contr&#244;le ActiveX (Visual C++) | Microsoft Docs"
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
  - "contrôles ActiveX (C++), ajouter des classes"
  - "classes (C++), créer"
ms.assetid: 729fcb37-54b8-44d5-9b4e-50bb16e0eea4
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Ajout d&#39;une classe &#224; partir d&#39;un contr&#244;le ActiveX (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Utilisez cet Assistant pour créer une classe MFC à partir d'une interface dans un contrôle ActiveX disponible.  Vous pouvez ajouter une classe MFC à une [application MFC](../mfc/reference/creating-an-mfc-application.md), à une [DLL MFC](../mfc/reference/creating-an-mfc-dll-project.md) ou à un [contrôle ActiveX MFC](../mfc/reference/creating-an-mfc-activex-control.md).  
  
> [!NOTE]
>  Pour ajouter une classe à partir d'un contrôle ActiveX, il n'est pas nécessaire de créer un projet MFC avec l'option Automation activée.  
  
 Un contrôle ActiveX est un composant logiciel réutilisable qui repose sur la notion de modèle d'objet composant \(COM, Component Object Model\), prend en charge une large gamme de fonctionnalités OLE et peut être personnalisé pour répondre à de nombreux besoins logiciels.  Les contrôles ActiveX sont conçus pour être utilisés à la fois dans des conteneurs de contrôles ActiveX ordinaires et sur Internet, dans des pages Web.  
  
### Pour ajouter une classe MFC à partir d'un contrôle ActiveX  
  
1.  Dans l'**Explorateur de solutions** ou dans l'[affichage de classes](http://msdn.microsoft.com/fr-fr/8d7430a9-3e33-454c-a9e1-a85e3d2db925), cliquez avec le bouton droit sur le nom du projet auquel vous souhaitez ajouter la classe du contrôle ActiveX.  
  
2.  Dans le menu contextuel, cliquez sur **Ajouter**, puis sur **Ajouter une classe**.  
  
3.  Dans le volet Modèles de la boîte de dialogue [Ajouter une classe](../ide/add-class-dialog-box.md), cliquez sur **Classe MFC à partir du contrôle ActiveX**, puis sur **Ouvrir** pour afficher l'[Assistant Ajout d'une classe à partir d'un contrôle ActiveX](../ide/add-class-from-activex-control-wizard.md).  
  
 Dans l'Assistant, vous pouvez ajouter plusieurs interfaces dans un contrôle ActiveX.  De même, vous pouvez créer des classes à partir de plusieurs contrôles ActiveX dans une session d'Assistant unique.  
  
 Vous pouvez ajouter des classes à partir des contrôles ActiveX inscrits dans votre système ou situés dans des fichiers bibliothèque de types \(.tlb, .olb, .dll, .ocx ou .exe\) sans passer au préalable par leur inscription dans votre système.  Pour plus d'informations sur l'inscription des contrôles ActiveX, consultez [Registering OLE Controls](../mfc/reference/registering-ole-controls.md).  
  
 L'Assistant crée une classe MFC, dérivée de [CWnd](../mfc/reference/cwnd-class.md) ou de [COleDispatchDriver](../mfc/reference/coledispatchdriver-class.md), pour chaque interface que vous ajoutez à partir du contrôle ActiveX sélectionné.  
  
## Voir aussi  
 [Contrôles ActiveX MFC](../mfc/mfc-activex-controls.md)   
 [Introduction to COM and ATL](../atl/introduction-to-com-and-atl.md)