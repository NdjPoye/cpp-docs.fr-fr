---
title: "Erreur irr&#233;cup&#233;rable C1033 | Microsoft Docs"
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
  - "C1033"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1033"
ms.assetid: 09976c03-8450-4cf7-8b43-1b91c2c2b9f9
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur irr&#233;cup&#233;rable C1033
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

impossible d'ouvrir la base de données pdb du programme  
  
 Cette erreur est peut\-être due à une erreur de disque.  
  
 Dans Visual C\+\+ .NET 2002, les paramètres régionaux de l'utilisateur doivent être définis correctement lorsque le nom du fichier \(ou le chemin d'accès au nom de fichier\) contient des caractères MBCS.  La définition des paramètres régionaux du système n'est pas suffisante ; il faut définir les paramètres régionaux utilisateur afin que les caractères MBCS puissent être traités.  
  
 Pour plus d'informations, consultez [http:\/\/support.microsoft.com\/default.aspx?scid\=kb;en\-us;246007](http://support.microsoft.com/default.aspx?scid=kb;en-us;246007).