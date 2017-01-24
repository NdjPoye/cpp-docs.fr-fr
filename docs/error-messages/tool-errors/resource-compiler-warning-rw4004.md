---
title: "Avertissement RW4004 du compilateur de ressources  | Microsoft Docs"
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
  - "RW4004"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RW4004"
ms.assetid: 596b6a89-9ce7-4ba7-bdcb-e8054c7efafa
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement RW4004 du compilateur de ressources 
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Caractère ASCII non équivalent au code de clé virtuelle  
  
 Un littéral de chaîne a été utilisé pour le code de clé virtuelle dans un accélérateur de type VIRTKEY.  
  
 Cet avertissement vous laisse poursuivre, mais notez que les touches accélérateur générées risquent de ne pas correspondre à la chaîne spécifiée. \(Les accélérateurs VIRTKEY et ASCII n'utilisent pas les mêmes codes de clé.\)  
  
 Si les littéraux de chaîne sont valides au niveau de la syntaxe, vous devez néanmoins utiliser les valeurs **VK\_\* \#define** dans WINDOWS.h pour être sûr d'obtenir l'accélérateur voulu.