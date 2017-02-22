---
title: "CA2AEX, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CA2AEX<t_nBufferLength>"
  - "CA2AEX"
  - "ATL.CA2AEX<t_nBufferLength>"
  - "ATLCONV/CA2AEX"
  - "ATL.CA2AEX"
  - "ATL::CA2AEX"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CA2AEX (classe)"
ms.assetid: 57dc65df-d9cf-4a84-99d3-6e031dde3664
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CA2AEX, classe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe est utilisée par les macros de conversion de chaînes `CA2TEX` et `CT2AEX`, et le typedef **CA2A**.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
      template<  
int t_nBufferLength= 128  
>  
class CA2AEX  
```  
  
#### Paramètres  
 `t_nBufferLength`  
 La taille de la mémoire tampon utilisée dans le processus de traduction.  La longueur par défaut est de 128 octets.  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CA2AEX::CA2AEX](../Topic/CA2AEX::CA2AEX.md)|Constructeur.|  
|[CA2AEX::~CA2AEX](../Topic/CA2AEX::~CA2AEX.md)|Le destructeur.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CA2AEX::operator LPSTR](../Topic/CA2AEX::operator%20LPSTR.md)|Opérateur de conversion.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CA2AEX::m\_psz](../Topic/CA2AEX::m_psz.md)|La donnée membre qui stocke la chaîne source.|  
|[CA2AEX::m\_szBuffer](../Topic/CA2AEX::m_szBuffer.md)|Le tampon statique, utilisé pour stocker la chaîne convertie.|  
  
## Notes  
 À moins que la fonctionnalité supplémentaire est requise, utilisez `CA2TEX`, `CT2AEX`, ou **CA2A** dans votre propre code.  
  
 Cette classe contient un tampon statique de taille fixe qui est utilisé pour stocker le résultat de la conversion.  Si le résultat est trop grand pour s'insérer dans la mémoire tampon statique, la classe alloue de la mémoire à `malloc`, libération de la mémoire lorsque l'objet est hors de portée.  Cela garantit que, contrairement aux macros de conversion de texte disponibles dans les versions antérieures ATL, il est sécurisée utiliser cette classe dans les boucles et qu'il ne débordera pas la pile.  
  
 Si les tests de la classe pour allouer de la mémoire sur le tas et de échec, il appellera `AtlThrow` avec un argument d' **E\_OUTOFMEMORY**.  
  
 Par défaut, les classes de conversion ATL et les macros utilisent la page de codes ANSI du thread actuel de la conversion.  
  
 Les macros suivantes sont basés sur cette classe :  
  
-   `CA2TEX`  
  
-   `CT2AEX`  
  
 Le typedef suivant est basé sur cette classe :  
  
-   **CA2A**  
  
 Pour une discussion sur ces macros de conversion de texte, consultez [Macros de conversion de chaînes ATL et MFC](../Topic/ATL%20and%20MFC%20String%20Conversion%20Macros.md).  
  
## Exemple  
 Consultez [Macros de conversion de chaînes ATL et MFC](../Topic/ATL%20and%20MFC%20String%20Conversion%20Macros.md) pour un exemple d'utilisation de ces macros de conversion de chaînes.  
  
## Configuration requise  
 **Header:** atlconv.h  
  
## Voir aussi  
 [CA2CAEX, classe](../../atl/reference/ca2caex-class.md)   
 [CA2WEX, classe](../../atl/reference/ca2wex-class.md)   
 [CW2AEX, classe](../../atl/reference/cw2aex-class.md)   
 [CW2CWEX, classe](../../atl/reference/cw2cwex-class.md)   
 [CW2WEX, classe](../../atl/reference/cw2wex-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)