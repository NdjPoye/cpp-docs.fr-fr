---
title: "CManualAccessor::CreateAccessor | Microsoft Docs"
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
  - "ATL::CManualAccessor::CreateAccessor"
  - "CreateAccessor"
  - "ATL.CManualAccessor.CreateAccessor"
  - "CManualAccessor.CreateAccessor"
  - "CManualAccessor::CreateAccessor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateAccessor (méthode)"
ms.assetid: 594c8d6d-b49a-4818-a9a5-81c8115d4e42
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CManualAccessor::CreateAccessor
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Attribue la mémoire pour les structures de colonnes de lien et initialise les colonnes des données des membres.  
  
## Syntaxe  
  
```  
  
      HRESULT CreateAccessor(   
   int nBindEntries,   
   void* pBuffer,   
   DBLENGTH nBufferSize    
) throw( );  
```  
  
#### Paramètres  
 `nBindEntries`  
 \<nombre de colonnes\>  Ce nombre doit correspondre au nombre d'appels à la fonction [CManualAccessor::AddBindEntry](../../data/oledb/cmanualaccessor-addbindentry.md).  
  
 `pBuffer`  
 \[in\] Un pointeur vers la mémoire tampon dans laquelle les colonnes de sortie sont stockées.  
  
 `nBufferSize`  
 \[in\] Taille de la mémoire tampon en octets.  
  
## Valeur de retour  
 Une des valeurs standard `HRESULT`.  
  
## Notes  
 Appelez cette fonction avant d'appeler la fonction `CManualAccessor::AddBindEntry`.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CManualAccessor, classe](../../data/oledb/cmanualaccessor-class.md)   
 [Exemple de DBViewer](../../top/visual-cpp-samples.md)