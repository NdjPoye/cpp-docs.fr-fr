---
title: "Gestion du bouton Appliquer | Microsoft Docs"
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
  - "bouton Appliquer dans une feuille de propriétés"
  - "feuilles de propriétés, bouton Appliquer"
ms.assetid: 7e977015-59b8-406f-b545-aad0bfd8d55b
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Gestion du bouton Appliquer
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les feuilles de propriétés ont une fonction que les boîtes de dialogue standard n'ont pas : Elles permettent à l'utilisateur d'appliquer les modifications qu'elles ont été effectuées avant de fermer la feuille de propriétés.  Cette opération s'effectue à l'aide du bouton Appliquer.  Cet article décrit les méthodes que vous pouvez utiliser pour implémenter cette fonctionnalité correctement.  
  
 Les boîtes de dialogue modales sont généralement des paramètres d'un objet externe lorsque l'utilisateur clique sur OK pour fermer la boîte de dialogue.  Il en va de même pour une feuille de propriétés : Lorsque l'utilisateur clique sur OK, les nouveaux paramètres dans la feuille de propriétés prennent effet.  
  
 Toutefois, vous pouvez permettre à l'utilisateur d'enregistrer des paramètres sans avoir à fermer la boîte de dialogue de la feuille de propriétés.  Il s'agit de la fonction du bouton Appliquer.  Le bouton appliquer applique les paramètres dans toutes les pages de propriétés de l'objet externe, par opposition au fait d'appliquer uniquement les paramètres de la page actuellement active.  
  
 Par défaut, le bouton de l'application reste désactivé.  Vous devez écrire du code pour activer le bouton appliquer aux moments appropriés, et vous devez écrire du code pour implémenter l'effet d'Appliquer, comme expliqué ci\-dessous.  
  
 Si vous ne souhaitez pas offrir de fonctionnalité Appliquer à l'utilisateur, il n'est pas nécessaire de supprimer le bouton d'application.  Vous pouvez la laisser désactivé, comme ce serait commun chez les applications qui utilisent la prise en charge standard de feuille de propriétés disponibles dans les versions futures de Windows.  
  
 Pour enregistrer une page comme modifiée et activer le bouton d'application, appelez **CPropertyPage::SetModified\( TRUE \)**.  Si l'une des pages rapporte une modification, le bouton de l'application reste activé, indépendamment de si la page active a été modifiée.  
  
 Vous devez appeler [CPropertyPage::SetModified](../Topic/CPropertyPage::SetModified.md) dès que l'utilisateur modifie tous les paramètres de la page.  Une méthode pour détecter lorsqu'un utilisateur modifie un paramètre dans la page consiste à implémenter des gestionnaires de notification de modification de ces contrôles dans la page de propriétés, telle que **EN\_CHANGE** ou **BN\_CLICKED**.  
  
 Pour implémenter l'effet du bouton d'appliquer, la feuille de propriétés doit indiquer son propriétaire, ou un autre objet externe dans l'application, pour appliquer les paramètres dans les pages de propriétés.  En même temps, la feuille de propriétés doit désactiver le bouton de l'application en appelant **CPropertyPage::SetModified\( FALSE \)** pour toutes les pages qui ont appliqué leurs modifications apportées à l'objet externe.  
  
 Pour obtenir un exemple de ce processus, consultez dans la rubrique MFC l'exemple général [PROPDLG](../top/visual-cpp-samples.md).  
  
## Voir aussi  
 [Feuilles de propriétés](../mfc/property-sheets-mfc.md)