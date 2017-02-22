---
title: "Implementing a Dialog Box | Microsoft Docs"
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
  - "ATL, boîtes de dialogue"
  - "CAxDialogImpl class, implementing dialog boxes in ATL"
  - "CSimpleDialog class, implementing dialog boxes in ATL"
  - "boîtes de dialogue, ATL"
ms.assetid: 478525f2-aa6a-435a-b162-68fc8aa98a8e
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Implementing a Dialog Box
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Il existe deux façons d'ajouter une boîte de dialogue ATL à votre projet : utilisez l'Assistant Dialogue ATL ou ajoutez \-le manuellement.  
  
## Ajouter une boîte de dialogue à l'aide de Dialogue ATL  
 Dans [ajoutez la boîte de dialogue de classe](../ide/add-class-dialog-box.md), sélectionnez l'objet dialog ATL pour ajouter une boîte de dialogue à votre projet ATL.  Remplissez Assistant Dialogue ATL en conséquence et cliquez sur **Finish**.  l'assistant ajoute une classe dérivée de [CAxDialogImpl](../atl/reference/caxdialogimpl-class.md) à votre projet.  Ouvrez l'affichage des ressources de menu **Affichage** , localisez votre dialogue, et double\-cliquez dessus pour l'ouvrir dans l'éditeur de ressources.  
  
> [!NOTE]
>  Si votre boîte de dialogue est dérivée d' `CAxDialogImpl`, il peut héberger des contrôles ActiveX et Windows.  Si vous ne souhaitez pas la charge mémoire de la prise en charge de contrôles ActiveX dans votre classe de boîte de dialogue, utilisez [CSimpleDialog](../atl/reference/csimpledialog-class.md) ou [CDialogImpl](../atl/reference/cdialogimpl-class.md) à la place.  
  
 Le message et les gestionnaires d'événements peuvent être ajoutés à votre classe de boîte de dialogue de l'Affichage de classes.  Pour plus d'informations, consultez [Ajout d'un gestionnaire de messages ATL](../atl/adding-an-atl-message-handler.md).  
  
## Ajout d'une boîte de dialogue manuellement  
 Implémenter une boîte de dialogue est semblable à implémenter une fenêtre.  Vous dérivez une classe de [CAxDialogImpl](../atl/reference/caxdialogimpl-class.md), de [CDialogImpl](../atl/reference/cdialogimpl-class.md), ou de [CSimpleDialog](../atl/reference/csimpledialog-class.md) et déclarez [table des messages](../atl/message-maps-atl.md) messages de handle.  Toutefois, vous devez également spécifier un ID de ressource modèle de boîte de dialogue dans votre classe dérivée.  Votre classe doit avoir un membre appelée `IDD` pour stocker cette valeur.  
  
> [!NOTE]
>  Lorsque vous créez une boîte de dialogue à l'aide de l'Assistant Dialogue ATL, l'assistant ajoute automatiquement le membre d' `IDD` comme type d' `enum` .  
  
 `CDialogImpl` vous permet d'implémenter un modal ou une boîte de dialogue non modale qui héberge des contrôles Windows.  `CAxDialogImpl` vous permet d'implémenter un modal ou une boîte de dialogue non modale qui héberge des contrôles ActiveX et Windows.  
  
 Pour créer une boîte de dialogue modale, créez une instance de votre `CDialogImpl`\(\)dérivé\) la classe dérivée \(ou `CAxDialogImpl`et appelez la méthode de [DoModal](../Topic/CDialogImpl::DoModal.md) .  Pour fermer la boîte de dialogue modale, appelez la méthode d' [EndDialog](../Topic/CDialogImpl::EndDialog.md) d'un gestionnaire de messages.  Pour créer une boîte de dialogue non modale, appelez la méthode de création au lieu d' `DoModal`.  Pour détruire une boîte de dialogue non modale, appelez [DestroyWindow](../Topic/CDialogImpl::DestroyWindow.md).  
  
 Jambage descendant des événements est automatiquement effectuée dans [CAxDialogImpl](../atl/reference/caxdialogimpl-class.md).  Implémentez les gestionnaires de messages de la boîte de dialogue lorsque vous les gestionnaires dans `CWindowImpl`classe dérivée.  Si une valeur de retour de message\- spécifique, renvoyez\- la comme `LRESULT`.  Les valeurs retournées par `LRESULT` sont mappées par ATL pour la gestion appropriée par le gestionnaire de dialogue windows.  Pour plus d'informations, consultez le code source de [CDialogImplBaseT::DialogProc](../Topic/CDialogImpl::DialogProc.md) dans atlwin.h.  
  
## Exemple  
 La classe suivante implémente une boîte de dialogue :  
  
 [!code-cpp[NVC_ATL_Windowing#66](../atl/codesnippet/CPP/implementing-a-dialog-box_1.h)]  
  
## Voir aussi  
 [classes de fenêtre](../atl/atl-window-classes.md)