---
title: "Utilisation de l&#39;Explorateur d&#39;objets OLE/COM | Microsoft Docs"
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
  - "contrôles ActiveX (C++), afficher des interfaces internes"
  - "Explorateur d'objets pour les objets Automation"
  - "Explorateur d'objets OLE/COM"
ms.assetid: a3359e31-2869-451d-9571-129b4e8b41f0
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Utilisation de l&#39;Explorateur d&#39;objets OLE/COM
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vous pouvez utiliser l'explorateur d'objets OLE et COM pour afficher les interfaces de contrôle.  
  
### Pour utiliser l'Explorateur d'objets OLE\/COM  
  
1.  Démarrez l'explorateur d'objets OLE et COM \(oleview.exe\), qui se trouve dans \\program files \(x86\)\\Windows Kits\\8.0\\bin\\x86\\dossier.  
  
2.  Dans le **Classes d'objets, groupés par composants** catégorie dans visionneur, ouvrez le **Objets Automation** dossier pour regarder les objets Automations enregistrés.  
  
3.  Sélectionnez l'un des contrôles.  Plusieurs onglets apparaissent alors dans le volet de droite; les interfaces qui sont implémentées par le contrôle s'affichent sur **Registry**.  
  
    -   Si vous ouvrez le raccourci du menu pour un contrôle dans le volet de gauche et après ouvrez **Voir Types Informations**, l'Explorateur ITypeInfo affiche une version reconstruite du fichier .idl ou .odl.  
  
    -   Si vous développez le nœud du contrôle dans le volet de gauche, vous obtenez une liste d'interfaces de l'objet.  Si vous sélectionnez une interface, son entrée du Registre est affichée dans le volet droit.  
  
    -   Si vous ouvrez le raccourci du menu pour un contrôle dans le volet de gauche et après ouvrez **View**, l'Explorateur d'objets OLE\/COM affiche une boîte de dialogue indiquant le GUID \(identificateur universel unique\) de l'interface et une option permettant de visualiser des informations sur la bibliothèque de types, s'il y en a une.  Si vous sélectionnez **Voir Type Informations**, vous obtenez l'affichage d'une partie d'un fichier .idl reconstruit qui est spécifique à l'interface de l'Explorateur ITypeInfo.  
  
    -   Dans l'Explorateur ITypeInfo, vous pouvez sélectionner les signatures des méthodes d'accesseurs dans le volet de droite en développant l'arborescence et en cliquant sur un membre d'interface.  
  
## Voir aussi  
 [Utilisation des contrôles ActiveX](../../data/ado-rdo/using-activex-controls.md)