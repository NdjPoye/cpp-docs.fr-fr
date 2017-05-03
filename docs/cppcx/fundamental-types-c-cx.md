---
title: "Types fondamentaux (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "01/22/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c9f82907-25f2-440b-91d6-afb8dbd46ea6
caps.latest.revision: 14
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 14
---
# Types fondamentaux (C++/CX)
Outre les types intégrés C\+\+ standard, [!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)] \([!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]\) prend en charge le système de type défini par le l’architecture [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] en fournissant des typedefs pour les types fondamentaux [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] qui correspondent aux types C\+\+ standard.[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] implémente les types fondamentaux booléens, de caractère et numériques. Ces typedefs sont définis dans l’espace de noms `default` qui ne doit jamais être spécifié explicitement. En outre, [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] fournit des wrappers et des implémentations concrètes de certains types et interfaces [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)].  
  
## Types booléens et de caractère  
 Le tableau suivant répertorie les types intégrés booléens et de caractère, et leurs équivalents C\+\+ standard.  
  
|Espace de noms|Nom [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]|Définition|Nom C\+\+ standard|Plage de valeurs|  
|--------------------|----------------------------------------------------------------------|----------------|------------------------|----------------------|  
|Plateforme|Booléen|Valeur booléenne de 8 bits.|bool|`true` \(non nul\) et `false` \(nul\)|  
|default|char16|Valeur non numérique 16 bits qui représente un point de code Unicode \(UTF\-16\).|wchar\_t<br /><br /> ou<br /><br /> L’c’|\(Spécifié par la norme Unicode\)|  
  
## Types numériques  
 Le tableau suivant répertorie les types numériques intégrés. Les types numériques sont déclarés dans l’espace de noms `default` et sont des typedefs pour le type intégré C\+\+ correspondant. Tous les types intégrés C\+\+ \(long, par exemple\) ne sont pas nécessairement pris en charge dans [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]. Pour des raisons de clarté du code, nous vous recommandons d’utiliser le nom [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)].  
  
|Nom [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]|Définition|Nom C\+\+ standard|Plage de valeurs|  
|----------------------------------------------------------------------|----------------|------------------------|----------------------|  
|int8|Valeur numérique signée 8 bits.|signed char|De –128 à 127|  
|uint8|Valeur numérique non signée 8 bits.|unsigned char|De 0 à 255|  
|int16|Entier signé 16 bits.|short|De –32 768 à 32 767|  
|uint16|Entier non signé 16 bits.|unsigned short|De 0 à 65 535|  
|int32|Entier signé 32 bits.|int|De –2 147 483 648 à 2 147 483 647|  
|uint32|Entier 32 bits non signé.|unsigned int|De 0 à 4 294 967 295|  
|int64|Entier signé 64 bits.|long long \-ou\- \_\_int64|De –9 223 372 036 854 775 808 à 9 223 372 036 854 775 807|  
|uint64|Entier 64 bits non signé.|unsigned long long \-ou\- unsigned \_\_int64|De 0 à 18 446 744 073 709 551 615|  
|float32|Nombre à virgule flottante IEEE 754 32 bits.|float|3.4E \+\/\- 38 \(7 chiffres\)|  
|float64|Nombre à virgule flottante IEEE 754 64 bits.|double|1.7E \+\/\- 308 \(15 chiffres\)|  
  
## Types [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]  
 Le tableau suivant répertorie certains types supplémentaires définis par l’architecture [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] et sont intégrés à [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]. Object et String sont des types référence. Tous les autres sont des types valeur. Tous ces types sont déclarés dans l’espace de noms `Platform`. Pour obtenir une liste complète, consultez [Espace de noms de plateforme](../cppcx/platform-namespace-c-cx.md).  
  
|Nom|Définition|  
|---------|----------------|  
|Objet|Représente tous les types [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)].|  
|Chaîne|Série de caractères représentant du texte.|  
|Rect|Ensemble de quatre nombres à virgule flottante représentant l’emplacement et la taille d’un rectangle.|  
|SizeT|Paire ordonnée de nombres à virgule flottante qui spécifient la hauteur et la largeur.|  
|Point|Paire ordonnée de coordonnées x et y à virgule flottante qui définissent un point dans un plan à deux dimensions.|  
|Guid|Valeur non numérique 128 bits utilisée comme identificateur unique.|  
|UIntPtr|\(Uniquement réservé à un usage interne.\) Valeur non signée 64 bits utilisée comme pointeur.|  
|IntPtr|\(Uniquement réservé à un usage interne.\)  Valeur signée 64 bits utilisée comme pointeur.|  
  
## Voir aussi  
 [système de type](../cppcx/type-system-c-cx.md)