---
title: "Avertissement du compilateur C4335 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4335"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4335"
ms.assetid: e66467ad-a10b-4438-8c7c-e8e8d11d39bb
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Avertissement du compilateur C4335
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Format de fichier Mac détecté : convertissez le fichier source au format DOS ou UNIX  
  
 Le caractère d'arrêt de ligne de la première ligne d'un fichier source est de style Macintosh \('\\r'\), par opposition à UNIX \('\\n'\) ou à DOS \('\\r\\n'\).  
  
 Cet avertissement est toujours émis en tant qu'erreur.  Consultez le pragma [warning](../../preprocessor/warning.md) pour plus d'informations sur la désactivation de cet avertissement.  Par ailleurs, cet avertissement n'est émis qu'une fois par module \(compiland\).  Par conséquent, s'il existe plusieurs directives `#include` spécifiant des fichiers au format Macintosh, l'erreur C4335 n'est générée qu'une seule fois.  
  
 L'une des façons de générer des fichiers au format Macintosh consiste à utiliser les **Options d'enregistrement avancées** \(menu **Fichier**\) dans Visual Studio.  
  
## Exemple  
 L'exemple suivant génère l'erreur C4335 :  
  
```  
// C4335 expected  
#include "c4335.h"   // assume both include files are in Macintosh format  
#include "c4335_2.h"  
```