---
title: "CW2CWEX, classe | Microsoft Docs"
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
  - "CW2CWEX"
  - "ATL::CW2CWEX"
  - "ATL.CW2CWEX"
  - "ATL.CW2CWEX<t_nBufferLength>"
  - "ATL::CW2CWEX<t_nBufferLength>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CW2CWEX (classe)"
ms.assetid: d654b22b-05a6-410f-a0ec-9a2cbbb4cca7
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CW2CWEX, classe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe est utilisée par les macros de conversion de chaînes `CW2CTEX` et `CT2CWEX`, et le typedef `CW2W`.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
      template<  
int t_nBufferLength= 128  
>  
class CW2CWEX  
```  
  
#### Paramètres  
 `t_nBufferLength`  
 La taille de la mémoire tampon utilisée dans le processus de traduction.  La longueur par défaut est de 128 octets.  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CW2CWEX::CW2CWEX](../Topic/CW2CWEX::CW2CWEX.md)|Constructeur.|  
|[CW2CWEX::~CW2CWEX](../Topic/CW2CWEX::~CW2CWEX.md)|Le destructeur.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CW2CWEX::operator LPCWSTR](../Topic/CW2CWEX::operator%20LPCWSTR.md)|Opérateur de conversion.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CW2CWEX::m\_psz](../Topic/CW2CWEX::m_psz.md)|La donnée membre qui stocke la chaîne source.|  
  
## Notes  
 À moins que la fonctionnalité supplémentaire est requise, utilisez `CW2CTEX`, `CT2CWEX`, ou `CW2W` dans votre code.  
  
 Cette classe est sécurisée à utiliser dans les boucles et ne débordera pas la pile.  Par défaut, les classes de conversion ATL et les macros utilisent la page de codes ANSI du thread actuel de la conversion.  
  
 Les macros suivantes sont basés sur cette classe :  
  
-   `CW2CTEX`  
  
-   `CT2CWEX`  
  
 Le typedef suivant est basé sur cette classe :  
  
-   `CW2W`  
  
 Pour une discussion sur ces macros de conversion de texte, consultez [Macros de conversion de chaînes ATL et MFC](../Topic/ATL%20and%20MFC%20String%20Conversion%20Macros.md).  
  
## Exemple  
 Consultez [Macros de conversion de chaînes ATL et MFC](../Topic/ATL%20and%20MFC%20String%20Conversion%20Macros.md) pour un exemple d'utilisation de ces macros de conversion de chaînes.  
  
## Configuration requise  
 **Header:** atlconv.h  
  
## Voir aussi  
 [CA2AEX, classe](../../atl/reference/ca2aex-class.md)   
 [CA2CAEX, classe](../../atl/reference/ca2caex-class.md)   
 [CA2WEX, classe](../../atl/reference/ca2wex-class.md)   
 [CW2AEX, classe](../../atl/reference/cw2aex-class.md)   
 [CW2WEX, classe](../../atl/reference/cw2wex-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)