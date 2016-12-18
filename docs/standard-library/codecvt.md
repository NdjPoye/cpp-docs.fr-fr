---
title: "&lt; codecvt &gt; | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "codecvt"
  - "std::<codecvt>"
  - "std.<codecvt>"
  - "<codecvt>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "codecvt (en-tête)"
ms.assetid: d44ee229-00d5-4761-9b48-0c702122789d
caps.latest.revision: 21
caps.handback.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt; codecvt &gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Définit plusieurs classes de modèle qui décrivent les objets en fonction de la classe de modèle [codecvt](../standard-library/codecvt-class.md). Ces objets peuvent servir de [facettes de paramètres régionaux](../standard-library/locale-class.md#facet_class) que contrôler les conversions entre une séquence de valeurs de type `Elem` et une séquence de valeurs de type `char`.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
#include <codecvt>  
  
```  
  
## <a name="remarks"></a>Remarques  
 Les facettes de paramètres régionaux déclarées dans cet en-tête convertir entre plusieurs codages de caractères. Pour les caractères larges (stockés dans le programme en entiers de taille fixe) :  
  
-   UCS-4 est au format Unicode (ISO 10646) codé dans le programme  
  
-   UCS-4 est au format Unicode (ISO 10646) codé dans le programme comme un entier de 32 bits.  
  
-   UCS-2 est Unicode encodée dans le programme  
  
-   UCS-2 est Unicode encodée dans le programme sous la forme d’un entier 16 bits.  
  
-   UTF-16 est Unicode encodée dans le programme en tant qu’un  
  
-   UTF-16 est Unicode encodée dans le programme en tant qu’un ou deux entiers 16 bits. (Notez que cela ne répond pas aux toutes les exigences d’un encodage de caractères larges valide des Standard C ou C++ Standard. Toutefois il est largement utilisé en tant que tel.)  
  
 Pour les flux d’octets (stockées dans un fichier, transmis sous la forme d’une séquence d’octets ou stockés dans le programme dans un tableau de `char`) :  
  
-   UTF-8 est encodé en Unicode  
  
-   Unicode encodée au sein d’un flux d’octets sous la forme d’un ou plusieurs octets 8 bits avec un ordre d’octet déterministe est UTF-8.  
  
-   UTF-16LE est encodé en Unicode  
  
-   UTF-16LE est Unicode encodée dans un flux d’octets au format UTF-16 avec chaque entier 16 bits affiche deux octets de 8 bits, moins significatif.  
  
-   UTF-16BE est encodé en Unicode  
  
-   UTF-16BE est Unicode encodée dans un flux d’octets au format UTF-16 avec chaque entier 16 bits proposé avec deux octets de 8 bits, octet le plus significatif en premier lieu.  
  
### <a name="enumerations"></a>Énumérations  
  
|||  
|-|-|  
|[codecvt_mode](../Topic/%3Ccodecvt%3E%20enums.md#codecvt_mode_enumeration)|Spécifie les informations de configuration de facettes de paramètres régionaux.|  
  
### <a name="classes"></a>Classes  
  
|||  
|-|-|  
|[codecvt_utf8](../Topic/%3Ccodecvt%3E%20functions.md#codecvt_utf8)|Représente une facette de paramètres régionaux qui effectue la conversion entre des caractères larges encodées sous la forme UCS-2 ou UCS-4 et un flux d’octets encodée en UTF-8.|  
|[codecvt_utf8_utf16](%3Ccodecvt%3E%20functions.md#codecvt_utf8_utf16)|Représente une facette de paramètres régionaux qui effectue la conversion entre encodé en UTF-16 de caractères larges et un flux d’octets encodée en UTF-8.|  
|[codecvt_utf16](../Topic/%3Ccodecvt%3E%20functions.md#codecvt_utf16)|Représente une facette de paramètres régionaux qui effectue la conversion entre des caractères larges encodées sous la forme UCS-2 ou UCS-4 et un flux d’octets encodée en UTF-16LE ou UTF-16BE.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \< codecvt>  
  
 **Namespace :** stdt  
  
## <a name="see-also"></a>Voir aussi  
 [Référence de fichiers d’en-tête](../standard-library/cpp-standard-library-header-files.md)




