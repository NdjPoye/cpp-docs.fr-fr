---
title: "CDumpContext Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDumpContext"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AfxDump object"
  - "CDumpContext class"
  - "diagnostic, diagnostic classes"
  - "diagnostic classes"
  - "diagnostics, diagnostic classes"
ms.assetid: 98c52b2d-14b5-48ed-b423-479a4d1c60fa
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CDumpContext Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Prend en charge la sortie de diagnostic en continu sous forme de texte explicite.  
  
## Syntaxe  
  
```  
class CDumpContext  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CDumpContext::CDumpContext](../Topic/CDumpContext::CDumpContext.md)|Construit un objet `CDumpContext`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CDumpContext::DumpAsHex](../Topic/CDumpContext::DumpAsHex.md)|Du fait dumping sur l'élément indiqué au format hexadécimal.|  
|[CDumpContext::Flush](../Topic/CDumpContext::Flush.md)|Vide toutes les données dans la mémoire tampon de contexte de dump.|  
|[CDumpContext::GetDepth](../Topic/CDumpContext::GetDepth.md)|Obtient un entier correspondant à la profondeur du dump.|  
|[CDumpContext::HexDump](../Topic/CDumpContext::HexDump.md)|Fait un dump des octets contenus dans un tableau au format hexadécimal.|  
|[CDumpContext::SetDepth](../Topic/CDumpContext::SetDepth.md)|Définit la profondeur du dump.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CDumpContext::operator \<\<](../Topic/CDumpContext::operator%20%3C%3C.md)|Variables objets et des insertions dans le contexte de dump.|  
  
## Notes  
 `CDumpContext` n'a pas de classe de base.  
  
 Vous pouvez utiliser [afxDump](../Topic/afxDump%20\(CDumpContext%20in%20MFC\).md), un objet predeclared d' `CDumpContext` , pour la plupart de votre dump.  L'objet d' `afxDump` est disponible uniquement dans la version debug de la bibliothèque MFC.  
  
 Plusieurs de l'utilisation `afxDump` de [services de diagnostic](../../mfc/reference/diagnostic-services.md) de mémoire pour leur sortie.  
  
 Sous l'environnement Windows, la sortie de l'objet prédéfini d' `afxDump` , conceptuellement semblable au flux d' `cerr` , est routée vers le débogueur par l'intermédiaire de la fonction Windows **OutputDebugString**.  
  
 La classe d' `CDumpContext` un \(\)**\<\<**un opérateur d'insertion surchargé pour les pointeurs d' `CObject` qui fait un dump les données de l'objet.  Si vous avez besoin d'un format de dump personnalisé pour un objet dérivé, substituez [CObject::Dump](../Topic/CObject::Dump.md).  La plupart des classes MFC \(Microsoft Foundation implémentent une fonction membre substituée d' `Dump` .  
  
 Les classes qui ne sont pas dérivées d' `CObject`, tel qu' `CString`, `CTime`, et `CTimeSpan`, ont leurs propres opérateurs surchargés d'insertion d' `CDumpContext` , de même que rendent les structures souvent utilisées comme **CFileStatus**, `CPoint`, et `CRect`.  
  
 Si vous utilisez [IMPLEMENT\_DYNAMIC](../Topic/IMPLEMENT_DYNAMIC.md) macro ou d' [IMPLEMENT\_SERIAL](../Topic/IMPLEMENT_SERIAL.md) dans l'implémentation de votre classe, puis `CObject::Dump` imprimera le nom de votre `CObject`classe dérivée.  Sinon, elle imprimera `CObject`.  
  
 La classe d' `CDumpContext` est disponible avec les versions debug et Release versions de la bibliothèque, mais la fonction membre d' `Dump` est définie uniquement dans la version debug.  Utilisez **\#ifdef \_DEBUG** \/instructions d' `#endif` pour encadrer votre code de diagnostic, notamment les fonctions membres personnalisées d' `Dump` .  
  
 Avant de créer votre propre objet d' `CDumpContext` , vous devez créer un objet d' `CFile` qui sert de destination de dump.  
  
 Pour plus d'informations sur `CDumpContext`, consultez l' [Applications MFC de débogage](../Topic/MFC%20Debugging%20Techniques.md).  
  
 **\_DEBUG \#define**  
  
## Hiérarchie d'héritage  
 `CDumpContext`  
  
## Configuration requise  
 **Header:** afx.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CFile Class](../../mfc/reference/cfile-class.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)