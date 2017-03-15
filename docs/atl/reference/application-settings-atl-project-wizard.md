---
title: "Param&#232;tres de l’application, Assistant Projet&#160;ATL | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "vc.appwiz.atl.com.appset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Assistant Projet ATL, paramètres de l’application"
ms.assetid: d48c9fc5-f439-49fd-884c-8bcfa7d52991
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# Param&#232;tres de l’application, Assistant Projet&#160;ATL
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Utilisez la page **Paramètres de l'application** de l'Assistant Projet ATL pour concevoir des fonctionnalités de base et les ajouter à un nouveau projet ATL.  
  
## Type de serveur  
 Choisissez l'un de ces trois types de serveur :  
  
 **Bibliothèque de liens dynamiques \(DLL\)**  
 Sélectionnez ce type pour créer un serveur in\-process.  
  
 **Exécutable \(EXE\)**  
 Sélectionnez ce type pour créer un serveur out\-of\-process local.  Cette option ne permet pas la prise en charge de MFC ou de COM\+ 1.0.  Elle ne permet pas non plus la fusion du code proxy\/stub.  
  
 **Service \(EXE\)**  
 Sélectionnez ce type pour créer une application Windows qui s'exécute en arrière\-plan au démarrage de Windows.  Cette option ne permet pas la prise en charge de MFC ou COM\+ 1.0, ni la fusion de code de proxy\/stub.  
  
## Options supplémentaires  
  
> [!NOTE]
>  Toutes les options supplémentaires ne sont disponibles que pour les projets DLL.  
  
 **Permettre la fusion de code de proxy\/stub**  
 Activez la case à cocher **Permettre la fusion de code de proxy\/stub** lorsque le marshaling des interfaces est requis.  Cette option met le proxy généré par MIDL et le code stub dans le même exécutable que le serveur.  
  
 **MFC du support technique**  
 Sélectionnez cette option pour spécifier que votre objet offre une prise en charge des MFC.  Cette option lie votre projet aux bibliothèques MFC, ce qui vous permet d'accéder à toutes les classes et fonctions qu'elles contiennent.  
  
 **Prise en charge COM\+ 1.0**  
 Sélectionnez cette option pour modifier les paramètres de génération de votre projet afin de prendre en charge les composants COM\+ 1.0.  En plus des bibliothèques standard, l'Assistant ajoute la bibliothèque comsvcs.lib, spécifique aux composants COM\+ 1.0.  
  
 En outre, le chargement de la bibliothèque mtxex.dll sur le système hôte est différé au démarrage de votre application.  
  
-   **Registre des composants de charge** Si votre projet contient la prise en charge ATL COM\+ 1,0 composants, vous pouvez définir cette option.  L'inscription de composants permet à votre objet COM\+ 1.0 d'obtenir une liste des composants, d'inscrire des composants ou d'annuler l'inscription de composants \(individuellement ou tous en même temps\).  
  
## Voir aussi  
 [Assistant Projet ATL](../../atl/reference/atl-project-wizard.md)   
 [Création d'un projet ATL](../../atl/reference/creating-an-atl-project.md)   
 [Configurations des projets ATL par défaut](../../atl/reference/default-atl-project-configurations.md)