---
title: "Erreur irr&#233;cup&#233;rable C1001 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1001"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1001"
ms.assetid: 5736cdb3-22c8-4fad-aa85-d5e0d2b232f4
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# Erreur irr&#233;cup&#233;rable C1001
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ERREUR INTERNE DU COMPILATEUR \(fichier compilateur, ligne numéro\) Choisissez la commande Support technique du menu ? \(Aide\) de Visual C\+\+ ou ouvrez le fichier d'aide du Support technique pour plus d'informations  
  
 Le compilateur ne peut pas générer de code correct pour une construction, sans doute à cause de la combinaison d'une option d'optimisation avec une expression.  Essayez d'enlever une ou plusieurs options d'optimisation et de recompiler la fonction contenant la ligne indiquée dans le message d'erreur.  
  
 Vous pouvez corriger le problème en supprimant une ou plusieurs options d'optimisation.  Pour déterminer l'option en cause, supprimez les options une par une et recompilez jusqu'à la disparition du message d'erreur.  Les options les plus souvent en cause sont **\/Og**, **\/Oi** et `/Oa`.  Dès que vous avez déterminé l'option responsable, vous pouvez la désactiver à l'aide du pragma [optimize](../../preprocessor/optimize.md) pour la fonction où apparaît l'erreur et continuer à utiliser cette option dans le reste du module.  
  
 La base de connaissances Microsoft détient plus d'informations à propos du C1001; consultez [http:\/\/support.microsoft.com\/default.aspx?scid\=kb;en\-us;134650](http://support.microsoft.com/default.aspx?scid=kb;en-us;134650).  
  
 Essayez de réécrire la ligne où l'erreur est signalée ou les quelques lignes qui entourent celle\-ci.