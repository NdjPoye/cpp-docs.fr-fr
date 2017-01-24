---
title: "Erreur irr&#233;cup&#233;rable RC1015 du compilateur de ressources  | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "RC1015"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RC1015"
ms.assetid: 23f187e1-5538-40b5-9042-edd2888f55c2
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur irr&#233;cup&#233;rable RC1015 du compilateur de ressources 
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

impossible d'ouvrir le fichier Include 'nomfichier'  
  
 Le fichier include spécifié n'existe pas, il ne peut pas être ouvert ou il est introuvable.  
  
 Assurez\-vous que les paramètres d'environnement sont corrects et que vous avez spécifié le chemin d'accès approprié pour le fichier.  Vérifiez que le compilateur de ressources a accès à un nombre suffisant de handles de fichiers.  Si le fichier se trouve sur un lecteur réseau, assurez\-vous que vous avez les droits d'accès nécessaires au fichier.  
  
 RC1015 peut se produire même si le fichier include existe dans un répertoire spécifié comme Autre répertoire inclus dans la page de propriétés Propriétés de configuration \-\> Ressources \-\> Page de propriétés générales ; spécifiez le chemin d'accès complet au fichier include.  
  
 Pour plus d'informations, consultez l'article de la Base de connaissances Q326987 : RC1015 Error When Using Resource View If the Include Path is Too Long.