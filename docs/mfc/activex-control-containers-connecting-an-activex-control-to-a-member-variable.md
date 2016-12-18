---
title: "Conteneurs de contr&#244;les ActiveX&#160;: association d&#39;un contr&#244;le ActiveX &#224; une variable membre | Microsoft Docs"
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
  - "conteneurs de contrôles ActiveX (C++), accéder aux contrôles ActiveX"
  - "conteneurs de contrôles ActiveX (C++), contrôles ActiveX en tant que variables membres"
  - "contrôles ActiveX (C++), accéder"
  - "contrôles ActiveX (C++), variables membres de projet"
  - "connecter des contrôles ActiveX à des variables membres de conteneur"
  - "variables membres (C++), contrôles ActiveX dans un projet"
ms.assetid: 7898a336-440d-4a60-be43-cb062b807aee
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Conteneurs de contr&#244;les ActiveX&#160;: association d&#39;un contr&#244;le ActiveX &#224; une variable membre
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La façon la plus facile d'accéder à un contrôle ActiveX depuis l'application de conteneur de contrôle est d'associer le contrôle ActiveX à une variable membre de la classe de la boîte de dialogue qui contient le contrôle.  
  
> [!NOTE]
>  Il ne s'agit pas de la seule façon d'accéder à un contrôle incorporé depuis une classe de conteneur, mais dans le cadre de cet article cela suffit.  
  
### Ajouter une variable membre de la classe de la boîte de dialogue  
  
1.  Dans l'Affichage de classes, cliquez avec le bouton droit de la boîte de dialogue principale pour ouvrir le menu contextuel.  Par exemple, `CContainerDlg`.  
  
2.  Dans le menu contextuel, cliquez sur **Ajouter**, puis sur **Ajouter une variable**.  
  
3.  Dans l'Assistant Ajout de variable membre, cliquez sur **Variable du contrôle**.  
  
4.  Dans la zone de liste de **ID de contrôle**, sélectionnez l'ID du contrôle du contrôle ActiveX incorporé.  Par exemple, `IDC_CIRCCTRL1`.  
  
5.  Dans la zone **Nom de la variable**, tapez un nom.  
  
     Par exemple, `m_circctl`.  
  
6.  Cliquez sur **Terminer** pour accepter les options et pour quitter l'Assistant Ajout de variable membre.  
  
## Voir aussi  
 [Conteneurs de contrôles ActiveX](../mfc/activex-control-containers.md)