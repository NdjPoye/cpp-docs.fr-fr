---
title: Aucune liaison | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- no linkage
- linkage [C++], none
ms.assetid: 5a413082-1034-4e04-b76b-8d14668bf434
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: 278325c1ad1b31ce20b6a17034be5e4731f6da78
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="no-linkage"></a>Aucune liaison
Si une déclaration d'un identificateur dans un bloc n'inclut pas le spécificateur de classe de stockage `extern`, l'identificateur n'a aucune liaison et est propre à la fonction.  
  
 Les identificateurs suivants n'ont aucune liaison :  
  
-   Un identificateur déclaré comme autre chose qu'un objet ou une fonction  
  
-   un identificateur déclaré comme étant un paramètre de fonction  
  
-   Un identificateur de portée de bloc pour un objet déclaré sans spécificateur de classe de stockage `extern`  
  
 Si un identificateur n'a aucune liaison, une nouvelle déclaration du même nom (dans un spécificateur de déclarateur ou de type) au même niveau de portée génère une erreur de redéfinition de symbole.  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation d’extern pour spécifier la liaison](../cpp/using-extern-to-specify-linkage.md)
