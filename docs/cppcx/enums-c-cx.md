---
title: "&#201;num&#233;rations (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 99fbbe28-c1cd-43af-9ead-60f90eba6e68
caps.latest.revision: 14
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 14
---
# &#201;num&#233;rations (C++/CX)
[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] prend en charge le mot clé `public enum class`, qui est analogue à un `scoped  enum` C\+\+ standard. Lorsque vous utilisez un énumérateur qui est déclaré à l'aide du mot clé `public enum class`, vous devez utiliser l'identificateur d'énumération pour limiter chaque valeur de l'énumérateur.  
  
## Notes  
 Un `public enum class` qui n'a pas de spécificateur d'accès, tel que `public`, est traité comme un [scoped enum](../Topic/Enumerations%20\(C++\).md) C\+\+ standard.  
  
 Une déclaration `public enum class` ou `public enum struct` peut avoir un type sous\-jacent de n'importe quel type intégral bien que [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] lui\-même requiert que le type soit int32 ou uint32 pour un enum de bits. La syntaxe suivante décrit les éléments d'un `public enum class` ou d'un `public enum struct`. Pour plus d'informations, consultez [enum, classe](../Topic/enum%20class%20%20\(C++%20Component%20Extensions\).md).  
  
 Cet exemple montre comment définir une classe d'énumération publique :  
  
 [!code-cpp[cx_enums#01](../snippets/cpp/VS_Snippets_Misc/cx_enums/cpp/class1.h#01)]  
  
 L'exemple suivant montre comment le consommer :  
  
 [!code-cpp[cx_enums#02](../snippets/cpp/VS_Snippets_Misc/cx_enums/cpp/class1.h#02)]  
  
## Exemples  
 Les exemples suivants indiquent comment déclarer un enum,  
  
 [!code-cpp[cx_enums#03](../snippets/cpp/VS_Snippets_Misc/cx_enums/cpp/class1.h#03)]  
  
 L'exemple suivant indique comment effectuer un cast en équivalents numériques et effectuer des comparaisons. Notez que l'utilisation de l'énumérateur `One` est limitée par l'identificateur d'énumération `Enum1` et que l'énumérateur `First` est limité par `Enum2`.  
  
 [!code-cpp[cx_enums#04](../snippets/cpp/VS_Snippets_Misc/cx_enums/cpp/class1.h#04)]  
  
## Voir aussi  
 [système de type](../cppcx/type-system-c-cx.md)   
 [Référence du langage Visual C\+\+](../cppcx/visual-c-language-reference-c-cx.md)   
 [Référence aux espaces de noms](../cppcx/namespaces-reference-c-cx.md)