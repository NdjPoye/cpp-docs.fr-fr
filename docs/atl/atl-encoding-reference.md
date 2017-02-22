---
title: "R&#233;f&#233;rence d&#39;encodage ATL | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "encoder"
  - "encoder, fonctions"
ms.assetid: 82d4fdf3-3c4a-4fe2-b297-8ffb4714406f
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# R&#233;f&#233;rence d&#39;encodage ATL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'encodage dans une plage des normes web courants tels que l'uuencode, hexadécimal, et l'UTF8 en charge par le code trouvé dans atlenc.h.  
  
### Fonctions  
  
|||  
|-|-|  
|[AtlGetHexValue](../Topic/AtlGetHexValue.md)|Appelez cette fonction pour obtenir la valeur numérique d'un chiffre hexadécimal.|  
|[AtlHexDecode](../Topic/AtlHexDecode.md)|Décode une chaîne des données qui ont été encodées au format texte hexadécimal tel que par un appel précédent à [AtlHexEncode](../Topic/AtlHexEncode.md).|  
|[AtlHexDecodeGetRequiredLength](../Topic/AtlHexDecodeGetRequiredLength.md)|Appelez cette fonction pour obtenir la taille en octets de mémoire tampon pouvant contenir des données décodées d'une chaîne encodée hexa\- de la longueur spécifiée.|  
|[AtlHexEncode](../Topic/AtlHexEncode.md)|Appelez cette fonction pour encoder certaines données comme une chaîne de texte hexadécimal.|  
|[AtlHexEncodeGetRequiredLength](../Topic/AtlHexEncodeGetRequiredLength.md)|Appelez cette fonction pour obtenir la taille caractères d'une mémoire tampon qui peut contenir une chaîne encodée des données de la taille spécifiée.|  
|[AtlUnicodeToUTF8](../Topic/AtlUnicodeToUTF8.md)|Appelez cette fonction pour convertir une chaîne Unicode en UTF\-8.|  
|[BEncode](../Topic/BEncode.md)|Appelez cette fonction pour convertir des données à l'aide de l'encodage de « B ».|  
|[BEncodeGetRequiredLength](../Topic/BEncodeGetRequiredLength.md)|Appelez cette fonction pour obtenir la taille caractères d'une mémoire tampon qui peut contenir une chaîne encodée des données de la taille spécifiée.|  
|[EscapeXML](../Topic/EscapeXML.md)|Appelez cette fonction pour convertir des caractères qui ne sont pas sécurisé à utiliser dans le XML en leurs équivalents sécurisés.|  
|[GetExtendedChars](../Topic/GetExtendedChars.md)|Appelez cette fonction pour obtenir le nombre de caractères étendus dans une chaîne.|  
|[IsExtendedChar](../Topic/IsExtendedChar.md)|Appelez cette fonction pour déterminer si un caractère donné est un caractère étendu \(moins de 32, supérieur à 126, et non un onglet, un saut de ligne ou de retour chariot\)|  
|[QEncode](../Topic/QEncode.md)|Appelez cette fonction pour convertir des données à l'aide de l'encodage de « Q ».|  
|[QEncodeGetRequiredLength](../Topic/QEncodeGetRequiredLength.md)|Appelez cette fonction pour obtenir la taille caractères d'une mémoire tampon qui peut contenir une chaîne encodée des données de la taille spécifiée.|  
|[QPDecode](../Topic/QPDecode.md)|Décode une chaîne des données qui ont été encodées au format entre guillemets\- imprimable tel que par un appel précédent à [QPEncode](../Topic/QPEncode.md).|  
|[QPDecodeGetRequiredLength](../Topic/QPDecodeGetRequiredLength.md)|Appelez cette fonction pour obtenir la taille en octets de mémoire tampon pouvant contenir des données décodées de la chaîne entre guillemets\-imprimable\- encodée de la longueur spécifiée.|  
|[QPEncode](../Topic/QPEncode.md)|Appelez cette fonction pour encoder des données dans le format entre guillemets\- imprimable.|  
|[QPEncodeGetRequiredLength](../Topic/QPEncodeGetRequiredLength.md)|Appelez cette fonction pour obtenir la taille caractères d'une mémoire tampon qui peut contenir une chaîne encodée des données de la taille spécifiée.|  
|[Uudecode](../Topic/UUDecode.md)|Décode une chaîne des données qui uuencoded tel que par un appel précédent à [uuencode](../Topic/UUEncode.md).|  
|[UUDecodeGetRequiredLength](../Topic/UUDecodeGetRequiredLength.md)|Appelez cette fonction pour obtenir la taille en octets de mémoire tampon pouvant contenir des données décodées d'une chaîne uuencoded de la longueur spécifiée.|  
|[Uuencode](../Topic/UUEncode.md)|Appelez cette fonction à l'uuencode des données.|  
|[UUEncodeGetRequiredLength](../Topic/UUEncodeGetRequiredLength.md)|Appelez cette fonction pour obtenir la taille caractères d'une mémoire tampon qui peut contenir une chaîne encodée des données de la taille spécifiée.|  
  
### Macros  
  
|||  
|-|-|  
|[Balises d'ATL\_ESC](../Topic/ATL_ESC%20Flags.md)|Ces indicateurs sont utilisées pour contrôler le comportement d' [EscapeXML](../Topic/EscapeXML.md).|  
|[Balises d'ATLSMTP\_QPENCODE](../Topic/ATLSMTP_QPENCODE%20Flags.md)|Ces indicateurs indiquent dans quelle mesure l'encodage entre guillemets\- imprimable doit être effectué par [QPEncode](../Topic/QPEncode.md).|  
|[Balises d'ATLSMTP\_UUENCODE](../Topic/ATLSMTP_UUENCODE%20Flags.md)|Ces indicateurs décrivent comment uuencoding doit être effectué par [uuencode](../Topic/UUEncode.md).|  
  
## Voir aussi  
 [Concepts](../atl/active-template-library-atl-concepts.md)   
 [ATL COM Desktop Components](../atl/atl-com-desktop-components.md)