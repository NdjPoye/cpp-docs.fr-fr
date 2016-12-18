---
title: "Contr&#244;les ActiveX MFC&#160;: utilisation des pages de propri&#233;t&#233;s stock | Microsoft Docs"
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
  - "CLSID_CPicturePropPage"
  - "CLSID_CColorPropPage"
  - "CLSID_CFontPropPage"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLSID_CColorPropPage"
  - "CLSID_CFontPropPage"
  - "CLSID_CPicturePropPage"
  - "pages de propriétés stock de couleurs"
  - "polices, contrôles ActiveX"
  - "contrôles ActiveX MFC, pages de propriétés"
  - "pages de propriétés stock d'images"
  - "propriétés stock, pages de propriétés stock"
ms.assetid: 22638d86-ff3e-4124-933e-54b7c2a25968
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Contr&#244;les ActiveX MFC&#160;: utilisation des pages de propri&#233;t&#233;s stock
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article explique les pages de propriétés stock disponibles pour les contrôles ActiveX et comment les utiliser.  
  
 Pour plus d'informations sur l'utilisation des pages de propriétés d'un contrôle ActiveX, consultez les articles suivants :  
  
-   [Contrôles ActiveX MFC : pages de propriétés](../mfc/mfc-activex-controls-property-pages.md)  
  
-   [Contrôles ActiveX MFC : ajout d'une page de propriétés personnalisées](../mfc/mfc-activex-controls-adding-another-custom-property-page.md)  
  
 MFC fournit trois pages de propriétés à utiliser avec les contrôles ActiveX : **CLSID\_CColorPropPage**, **CLSID\_CFontPropPage**, et **CLSID\_CPicturePropPage**.  Ces pages affichent une interface utilisateur pour la couleur, la police, et les propriétés de l'image, respectivement.  
  
 Pour incorporer ces pages de propriétés à un contrôle, ajoutez leurs ID au code qui initialise le choix du contrôle d'ID de page de propriétés.  Dans l'exemple suivant, le code, situé dans le fichier d'implémentation du contrôle  \(.CPP\), initialise le tableau pour contenir les trois pages de propriétés et la page de propriétés par défaut \( `CMyPropPage` nommé dans cet exemple\) :  
  
 [!code-cpp[NVC_MFC_AxOpt#21](../mfc/codesnippet/CPP/mfc-activex-controls-using-stock-property-pages_1.cpp)]  
  
 Notez que le nombre de pages de propriétés, dans la macro `BEGIN_PROPPAGEIDS`, est égal à 4.  Cela représente le nombre de pages de propriétés prises en charge par le contrôle ActiveX.  
  
 Une fois ces modifications effectuées, recréez votre projet.  Votre contrôle a maintenant des pages de propriétés pour les propriétés de police, image, et de couleur.  
  
> [!NOTE]
>  Si les pages de propriétés d'actions ne sont pas accessibles, c'est peut\-être parce que la DLL MFC \(MFCxx.DLL\) n'a pas été correctement inscrit avec le système d'exploitation actuel.  Il résulte généralement de l''installation de Visual C\+\+ avec un système d'exploitation différent de celui en cours de exécution.  
  
> [!TIP]
>  Si les pages de propriétés stock ne sont pas visibles \(consultez la remarque précédente\), stockez la DLL en exécutant RegSvr32.exe de la ligne de commande avec le chemin d'accès complet vers la DLL.  
  
## Voir aussi  
 [Contrôles ActiveX MFC](../mfc/mfc-activex-controls.md)   
 [Contrôles ActiveX MFC : ajout de propriétés stock](../mfc/mfc-activex-controls-adding-stock-properties.md)