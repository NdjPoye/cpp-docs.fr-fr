---
title: "CA2WEX, classe | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATLCONV/CA2WEX"
  - "ATL.CA2WEX"
  - "ATL.CA2WEX<t_nBufferLength>"
  - "ATL::CA2WEX"
  - "ATL::CA2WEX<t_nBufferLength>"
  - "CA2WEX"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CA2WEX (classe)"
ms.assetid: 317d9ffb-e84f-47e8-beda-57e28fb19124
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CA2WEX, classe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe est utilisée par les macros de conversion de chaînes `CA2TEX`, `CA2CTEX`, `CT2WEX`, et `CT2CWEX`, et le typedef **CA2W**.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
      template<  
int t_nBufferLength= 128  
>  
class CA2WEX  
```  
  
#### Paramètres  
 `t_nBufferLength`  
 La taille de la mémoire tampon utilisée dans le processus de traduction.  La longueur par défaut est de 128 octets.  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CA2WEX::CA2WEX](../Topic/CA2WEX::CA2WEX.md)|Constructeur.|  
|[CA2WEX::~CA2WEX](../Topic/CA2WEX::~CA2WEX.md)|Le destructeur.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CA2WEX::operator LPWSTR](../Topic/CA2WEX::operator%20LPWSTR.md)|Opérateur de conversion.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CA2WEX::m\_psz](../Topic/CA2WEX::m_psz.md)|La donnée membre qui stocke la chaîne source.|  
|[CA2WEX::m\_szBuffer](../Topic/CA2WEX::m_szBuffer.md)|Le tampon statique, utilisé pour stocker la chaîne convertie.|  
  
## Notes  
 À moins que la fonctionnalité supplémentaire est requise, utilisez `CA2TEX`, `CA2CTEX`, `CT2WEX`, `CT2CWEX`, ou **CA2W** dans votre code.  
  
 Cette classe contient un tampon statique de taille fixe qui est utilisé pour stocker le résultat de la conversion.  Si le résultat est trop grand pour s'insérer dans la mémoire tampon statique, la classe alloue de la mémoire à `malloc`, libération de la mémoire lorsque l'objet est hors de portée.  Cela garantit que, contrairement aux macros de conversion de texte disponibles dans les versions antérieures ATL, il est sécurisée utiliser cette classe dans les boucles et qu'il ne débordera pas la pile.  
  
 Si les tests de la classe pour allouer de la mémoire sur le tas et de échec, il appellera `AtlThrow` avec un argument d' **E\_OUTOFMEMORY**.  
  
 Par défaut, les classes de conversion ATL et les macros utilisent la page de codes ANSI du thread actuel de la conversion.  Si vous souhaitez substituer ce comportement pour une conversion spécifique, spécifiez la page de codes comme second paramètre au constructeur de la classe.  
  
 Les macros suivantes sont basés sur cette classe :  
  
-   `CA2TEX`  
  
-   `CA2CTEX`  
  
-   `CT2WEX`  
  
-   `CT2CWEX`  
  
 Le typedef suivant est basé sur cette classe :  
  
-   **CA2W**  
  
 Pour une discussion sur ces macros de conversion de texte, consultez [Macros de conversion de chaînes ATL et MFC](../Topic/ATL%20and%20MFC%20String%20Conversion%20Macros.md).  
  
## Exemple  
 Consultez [Macros de conversion de chaînes ATL et MFC](../Topic/ATL%20and%20MFC%20String%20Conversion%20Macros.md) pour un exemple d'utilisation de ces macros de conversion de chaînes.  
  
## Configuration requise  
 **Header:** atlconv.h  
  
## Voir aussi  
 [CA2AEX, classe](../../atl/reference/ca2aex-class.md)   
 [CA2CAEX, classe](../../atl/reference/ca2caex-class.md)   
 [CW2AEX, classe](../../atl/reference/cw2aex-class.md)   
 [CW2CWEX, classe](../../atl/reference/cw2cwex-class.md)   
 [CW2WEX, classe](../../atl/reference/cw2wex-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)