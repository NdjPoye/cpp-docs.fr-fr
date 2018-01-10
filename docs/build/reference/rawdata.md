---
title: -RAWDATA | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /rawdata
dev_langs: C++
helpviewer_keywords:
- RAWDATA dumpbin option
- raw data
- -RAWDATA dumpbin option
- /RAWDATA dumpbin option
ms.assetid: 41cba845-5e1f-415e-9fe4-604a52235983
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 475ec5a827a1453a6f9474762d5be41299fc87e4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="rawdata"></a>/RAWDATA
```  
/RAWDATA[:{1|2|4|8|NONE[,number]]  
```  
  
## <a name="remarks"></a>Notes  
 Cette option affiche le contenu brut de chaque section dans le fichier. Les arguments de contrôlent le format de l’affichage, comme indiqué ci-dessous :  
  
|Argument|Résultat|  
|--------------|------------|  
|1|Valeur par défaut. Contenu est affiché dans les octets hexadécimaux et également en tant que caractères ASCII s’ils ont une représentation imprimée.|  
|2|Contenu s’affiche en tant que valeurs hexadécimales de 2 octets.|  
|4|Contenu s’affiche en tant que valeurs hexadécimales de 4 octets.|  
|8|Contenu s’affiche en tant que valeurs hexadécimales de 8 octets.|  
|AUCUN|Données brutes sont supprimées. Cet argument est utile pour contrôler la sortie de /ALL.|  
|*Nombre*|Les lignes affichées sont définies à une largeur qui contient `number` valeurs par ligne.|  
  
 Uniquement les [/HEADERS](../../build/reference/headers.md) (option DUMPBIN) est disponible pour les fichiers générés par le [/GL](../../build/reference/gl-whole-program-optimization.md) option du compilateur.  
  
## <a name="see-also"></a>Voir aussi  
 [DUMPBIN, options](../../build/reference/dumpbin-options.md)