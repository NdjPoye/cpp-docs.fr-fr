---
title: "Cr&#233;ation du contr&#244;le Tab | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "TCS_EX_REGISTERDROP"
  - "TCS_EX_FLATSEPARATORS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTabCtrl (classe), créer"
  - "contrôles onglet, créer"
  - "TCS_EX_FLATSEPARATORS (style étendu)"
  - "TCS_EX_REGISTERDROP (style étendu)"
ms.assetid: 3a9c2d64-f5f4-41ea-84ab-fceb73c3dbdc
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Cr&#233;ation du contr&#244;le Tab
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La création du contrôle d'onglet dépend de l'utilisation du contrôle dans une boîte de dialogue ou dans une fenêtre sans boîte de dialogue.  
  
### Pour utiliser CTabCtrl directement dans une boîte de dialogue  
  
1.  Dans l'éditeur de boîtes de dialogue, ajoutez un contrôle d'onglet dans votre ressource de modèle de dialogue.  Spécifiez son ID de contrôle  
  
2.  Utilisez l'[Assistant d'Ajout d'attribut](../ide/adding-a-member-variable-visual-cpp.md) pour ajouter un attribut de type [CTabCtrl](../mfc/reference/ctabctrl-class.md) avec la propriété de contrôle.  Vous pouvez utiliser ce membre pour appeler des méthodes `CTabCtrl`.  
  
3.  Fonctions gestionnaires de la carte dans la classe de dialogue pour tous les messages de notification de contrôle onglet à traiter.  Pour plus d'informations, consultez [Mappage de messages en fonctions](../mfc/reference/mapping-messages-to-functions.md).  
  
4.  Dans [OnInitDialog](../Topic/CDialog::OnInitDialog.md), définissez les styles pour `CTabCtrl`.  
  
### Pour utiliser CTabCtrl dans une fenêtre sans dialogue.  
  
1.  Définissez le contrôle d'une classe vue ou fenêtre.  
  
2.  Appelez la méthode [Create](../Topic/CTabCtrl::Create.md) du contrôle, éventuellement dans [OnInitialUpdate](../Topic/CView::OnInitialUpdate.md), éventuellement dans la fonction gestionnaire [OnCreate](../Topic/CWnd::OnCreate.md) de la fenêtre parente \(si vous sous\-classez le contrôle\).  Définissez les styles pour le contrôle.  
  
 Une fois que l'objet `CTabCtrl` a été créé, vous pouvez définir ou supprimer les styles étendus suivants :  
  
-   **TCS\_EX\_FLATSEPARATORS** Le contrôle onglet dessinera des séparateurs entre les éléments de l'onglet.  Ce style étendu affecte uniquement les contrôles onglet avec les styles **TCS\_BUTTONS** et **TCS\_FLATBUTTONS**.  Par défaut, créer le contrôle onglet avec le style **TCS\_FLATBUTTONS** définit le style étendu.  
  
-   **TCS\_EX\_REGISTERDROP** Le contrôle onglet génère des messages de notification de **TCN\_GETOBJECT** pour demander un objet de suppression de cible lorsqu'un objet est déplacé sur les éléments de l'onglet dans le contrôle.  
  
    > [!NOTE]
    >  Pour recevoir une notification de **TCN\_GETOBJECT**, vous devez initialiser les bibliothèques OLE par un appel à [AfxOleInit](../Topic/AfxOleInit.md).  
  
 Ces styles peuvent être récupérés et définis, une fois le contrôle créé, avec des appels respectifs aux méthodes [GetExtendedStyle](../Topic/CTabCtrl::GetExtendedStyle.md) et [SetExtendedStyle](../Topic/CTabCtrl::SetExtendedStyle.md).  
  
 Par exemple, définissez le style **TCS\_EX\_FLATSEPARATORS** avec les lignes de code suivantes :  
  
 [!code-cpp[NVC_MFCControlLadenDialog#33](../mfc/codesnippet/CPP/creating-the-tab-control_1.cpp)]  
  
 Désactivez le style **TCS\_EX\_FLATSEPARATORS** d'un objet `CTabCtrl` avec les lignes de code suivantes :  
  
 [!code-cpp[NVC_MFCControlLadenDialog#34](../mfc/codesnippet/CPP/creating-the-tab-control_2.cpp)]  
  
 Cela supprime les séparateurs qui apparaissent entre les boutons de votre objet `CTabCtrl`.  
  
## Voir aussi  
 [Utilisation de CTabCtrl](../mfc/using-ctabctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)