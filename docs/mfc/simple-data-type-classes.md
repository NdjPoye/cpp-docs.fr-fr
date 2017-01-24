---
title: "Classes de type de donn&#233;es simple | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.classes.data"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "classes de données (C++)"
  - "classes scalaires (C++)"
  - "classes de type de données simple"
ms.assetid: 0d591d68-0a33-49e9-8a6d-90c90de5c16a
caps.latest.revision: 12
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classes de type de donn&#233;es simple
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les classes suivantes encapsulent les coordonnées de dessin, chaînes de caractères, ainsi que des informations de date et d'heure, ce qui permet une utilisation pratique de la syntaxe C\+\+.  Ces objets sont largement utilisés comme paramètres des fonctions membres des classes windows dans la bibliothèque de classes.  Comme `CPoint`, `CSize`, et `CRect` correspondent au **POINT**, à la **TAILLE**, et aux structures `RECT`, respectivement, dans [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)], vous pouvez utiliser des objets de ces classes C\+\+ partout où vous pouvez utiliser ces structures de langage C.  Les classes fournissent des interfaces utiles à leurs fonctions membres.  `CStringT` fournit les chaînes de caractères dynamiques extrêmement flexibles.  `CTime`, `COleDateTime`, `CTimeSpan`, et **COleTimeSpan** représentent les valeurs de date et d'heure.  Pour plus d'informations sur ces classes, consultez l'article [Date et heure](../atl-mfc-shared/date-and-time.md).  
  
 Les classes qui commencent par «**COle**» sont des encapsulations des types de données fournis par OLE.  Ces types de données peuvent être utilisés dans des programmes Windows même si d'autres fonctionnalités OLE sont utilisées.  
  
 [CStringT Class](../atl-mfc-shared/reference/cstringt-class.md)  
 Contient des chaînes de caractères.  
  
 [CTime](../atl-mfc-shared/reference/ctime-class.md)  
 Contient des valeurs de date et d'heure absolues.  
  
 [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md)  
 Wrapper pour le type **DATE**OLE automation.  Représente les valeurs de date et d'heure.  
  
 [CTimeSpan](../atl-mfc-shared/reference/ctimespan-class.md)  
 Contient les valeurs de date et d'heure associées.  
  
 [COleDateTimeSpan](../atl-mfc-shared/reference/coledatetimespan-class.md)  
 Contient les valeurs de `COleDateTime` associées, telles que la différence entre deux valeurs de `COleDateTime`.  
  
 [CPoint](../atl-mfc-shared/reference/cpoint-class.md)  
 Contient des paires \(x, y\) de coordonnées.  
  
 [CSize](../atl-mfc-shared/reference/csize-class.md)  
 Contient la distance, les positions relatives, ou les valeurs couplées.  
  
 [CRect](../atl-mfc-shared/reference/crect-class.md)  
 Contient des coordonnées de zones rectangulaires.  
  
 [CImageList](../mfc/reference/cimagelist-class.md)  
 Fournit les fonctionnalités de la liste d'images Windows.  Les listes d'images sont utilisées avec des contrôles de liste et des contrôles d'arborescence.  Elles peuvent également être utilisées pour stocker et archiver un ensemble de bitmap de tailles identiques.  
  
 [COleVariant](../mfc/reference/colevariant-class.md)  
 Wrapper pour le type **VARIANT**OLE automation.  Les données dans **VARIANT**s peuvent être stockées dans plusieurs formats.  
  
 [COleCurrency](../mfc/reference/colecurrency-class.md)  
 Wrapper pour le type OLE **DEVISE**, un type OLE automation d'arithmétique à virgule fixe, avec 15 chiffres placés avant la virgule et 4 chiffres après.  
  
> [!NOTE]
>  À partir de Visual C\+\+ .NET, `CRect`, `CSize`, et `CPoint` ont été modifiés pour être utilisables dans les applications ATL ou MFC.  En outre, `CStringT` a été ajouté pour fournir une classe `CString` MFC indépendante.  Pour plus d'informations sur les classes utilitaires partagées, consultez [Classes partagées](../atl-mfc-shared/atl-mfc-shared-classes.md).  
  
## Voir aussi  
 [Vue d'ensemble des classes](../mfc/class-library-overview.md)