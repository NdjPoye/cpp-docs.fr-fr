---
title: "espace de noms par d&#233;faut | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "default_CPP"
dev_langs: 
  - "C++"
ms.assetid: 4712e9dc-57ba-43cc-811e-022e1dae4de8
caps.latest.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 6
---
# espace de noms par d&#233;faut
L’espace de noms `default` définit la portée des types intégrés pris en charge par [!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)] \([!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]\).  
  
## Syntaxe  
  
```  
namespace default;  
```  
  
## Membres  
 Tous les types intégrés héritent des membres suivants.  
  
|||  
|-|-|  
|[default::\(type\_name\)::Equals, méthode](../cppcx/default-type-name-equals-method.md)|Détermine si l'objet spécifié est identique à l'objet actuel.|  
|[default::\(type\_name\)::GetHashCode, méthode](../cppcx/default-type-name-gethashcode-method.md)|Retourne le code de hachage de cette instance.|  
|[default::\(type\_name\)::GetType, méthode](../cppcx/default-type-name-gettype-method.md)|Retourne une chaîne qui représente le type actuel.|  
|[default::\(type\_name\)::ToString, méthode](../cppcx/default-type-name-tostring-method.md)|Retourne une chaîne qui représente le type actuel.|  
  
### Types intégrés  
  
|Nom|Description|  
|---------|-----------------|  
|`char16`|Valeur non numérique 16 bits qui représente un point de code Unicode \(UTF\-16\).|  
|`float32`|Nombre à virgule flottante IEEE 754 32 bits.|  
|`float64`|Nombre à virgule flottante IEEE 754 64 bits.|  
|`int16`|Entier signé 16 bits.|  
|`int32`|Entier signé 32 bits.|  
|`int64`|Entier signé 64 bits.|  
|`int8`|Valeur numérique signée 8 bits.|  
|`uint16`|Entier non signé 16 bits.|  
|`uint32`|Entier non signé 32 bits.|  
|`uint64`|Entier non signé 64 bits.|  
|`uint8`|Valeur numérique non signée 8 bits.|  
  
## Configuration requise  
 **En\-tête :** vccorlib.h  
  
## Voir aussi  
 [Référence du langage Visual C\+\+](../cppcx/visual-c-language-reference-c-cx.md)