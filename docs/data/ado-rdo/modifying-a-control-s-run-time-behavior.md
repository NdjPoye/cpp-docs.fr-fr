---
title: "Modification du comportement d&#39;un contr&#244;le au moment de l&#39;ex&#233;cution | Microsoft Docs"
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
  - "contrôles ActiveX [C++], comportement au moment de l’exécution"
ms.assetid: 78b44b0f-0d5a-4da0-8aa2-595f5789c634
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Modification du comportement d&#39;un contr&#244;le au moment de l&#39;ex&#233;cution
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Après avoir [inséré un contrôle](../../data/ado-rdo/inserting-the-control-into-a-visual-cpp-application.md) et généré une ou plusieurs [classes wrapper](../../data/ado-rdo/wrapper-classes.md), vous pouvez appeler les méthodes du contrôle, et programmer les gestionnaires d’événements de ce dernier.  
  
 Les [classes wrapper](../../data/ado-rdo/wrapper-classes.md) du contrôle spécifient les fonctions que vous pouvez utiliser pour modifier son comportement au moment de l’exécution. Incluez le fichier d’en\-tête de classe wrapper approprié, et utilisez les méthodes. Pour définir une propriété, recherchez une méthode d’accesseur dont le nom de propriété est précédé de Set. Pour récupérer une propriété, recherchez une méthode d’accesseur dont le nom de propriété est précédé de Get. Vous pouvez écrire les gestionnaires d’événements plus tard.  
  
 Dans la mesure où les contrôles sont implémentés via Automation, les types passés ne peuvent être que des types compatibles Automation tels que BSTR et VARIANT. Bien que vous puissiez utiliser des appels système pour allouer et définir des types BSTR et VARIANT, vous pouvez utiliser les classes wrapper ATL \([CComBSTR](../../atl/reference/ccombstr-class.md), [CComVariant](../../atl/reference/ccomvariant-class.md)\), les classes wrapper de prise en charge du compilateur COM Visual C\+\+ \([\_bstr\_t](../../cpp/bstr-t-class.md), [\_variant\_t](../../cpp/variant-t-class.md)\), ou la classe wrapper MFC \([COleVariant](../../mfc/reference/colevariant-class.md)\).  
  
 Si vous ajoutez un contrôle de données, l’Assistant Insertion d’un contrôle ActiveX génère des classes wrapper pour les coclasses du contrôle de données qui gèrent ses objets de données internes. Ces classes n’incluent pas tous les contrôles RDO et ADO, mais représentent plutôt des objets internes déclarés dans la bibliothèque de types.  
  
 Si vous souhaitez utiliser ADO et RDO directement, vous devez vous connecter aux DLL ADO ou RDO directement \(Msado15.dll ou Msrdo20.dll\), soit avec les [classes de prise en charge COM du compilateur](../../cpp/compiler-com-support-classes.md), qui prennent en charge la [directive \#import](../../preprocessor/preprocessor-directives.md), soit avec le Kit de développement logiciel \(SDK\) correspondant.  
  
## Pour définir les propriétés de contrôle au moment de l’exécution  
 Notez que certaines propriétés d’un contrôle ActiveX peuvent être en lecture seule au moment de l’exécution, ce qui complique la création dynamique. Vous pouvez temporairement simuler le mode Design pour l’initialisation des propriétés en substituant le gestionnaire [OnAmbientPropertyChange](../Topic/COleControl::OnAmbientPropertyChange.md) du conteneur de contrôle, comme indiqué dans l’article de Base de connaissances consacré à la définition des propriétés au moment du design du contrôle ActiveX, au moment de l’exécution \(Q260744\). Les articles de la Base de connaissances sont sur [http:\/\/support.microsoft.com\/](http://support.microsoft.com/).  
  
## Voir aussi  
 [Utilisation des contrôles ActiveX](../../data/ado-rdo/using-activex-controls.md)