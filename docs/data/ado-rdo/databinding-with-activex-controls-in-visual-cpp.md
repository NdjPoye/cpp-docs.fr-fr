---
title: "Liaison de donn&#233;es avec des contr&#244;les ActiveX dans Visual&#160;C++ | Microsoft Docs"
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
  - "contrôles ActiveX (C++), liaison de données"
  - "contrôles dépendants (C++), ActiveX"
  - "contrôles (C++), liaison de données"
  - "liaison de données (C++), contrôles ActiveX"
  - "contrôles liés aux données (C++), ActiveX"
ms.assetid: afe11d2b-eefe-43ce-958d-82d3d4dee158
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Liaison de donn&#233;es avec des contr&#244;les ActiveX dans Visual&#160;C++
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La liaison de données est implémentée par l'intermédiaire de deux types de contrôles ActiveX : les contrôles de données et les contrôles liés aux données.  
  
 **Contrôles de données**  
 Un contrôle de données est responsable de l'encapsulation d'une requête de base de données et du jeu de lignes qui est récupéré.  Les contrôles de données Microsoft mettent en œuvre une interface utilisateur composée d'une série de boutons permettant d'effectuer des itérations au sein des données.  Visual C\+\+ offre deux technologies d'accès aux données pour les contrôles de données : [ADO et RDO](../../data/ado-rdo/data-access-ado-and-rdo.md).  
  
> [!IMPORTANT]
>  Les contrôles de données ADO et RDO sont une technologie plus ancienne fournie dans une version antérieure de Visual Studio et peuvent ne pas être disponibles dans votre version actuelle.  Pour utiliser les informations de cette section, vous devrez peut\-être obtenir une version antérieure pour obtenir le contrôle approprié.  
  
 **Contrôles liés aux données**  
 Un contrôle lié aux données est chargé de la présentation des données.  Les contrôles liés aux données se connectent aux contrôles de données pour recevoir les données et les présenter par le biais de diverses interfaces utilisateur.  Une application Visual C\+\+ peut également lier des variables aux valeurs de données définies dans les contrôles liés aux données ; consultez [CWnd::BindProperty](../Topic/CWnd::BindProperty.md).  
  
 Pour plus d'informations sur la liaison de données, consultez :  
  
-   [Contrôles ActiveX MFC : utilisation de la liaison de données dans un contrôle ActiveX](../../mfc/mfc-activex-controls-using-data-binding-in-an-activex-control.md)  
  
-   [Accès aux données : ADO et RDO](../../data/ado-rdo/data-access-ado-and-rdo.md)  
  
-   [Liaison de données ADO](../../data/ado-rdo/ado-databinding.md)  
  
-   [Liaison de données RDO](../../data/ado-rdo/rdo-databinding.md)  
  
-   [Classes wrapper](../../data/ado-rdo/wrapper-classes.md)  
  
-   [Définition de gestionnaires d'événements pour les contrôles ActiveX](../../data/ado-rdo/setting-event-handlers-on-activex-controls.md)  
  
-   [Interception des erreurs](../../data/ado-rdo/error-trapping.md)  
  
-   [Limites de la liaison de données](../../data/ado-rdo/limitations-of-databinding.md)  
  
## Voir aussi  
 [Contrôles liés aux données \(ADO et RDO\)](../../data/ado-rdo/data-bound-controls-ado-and-rdo.md)