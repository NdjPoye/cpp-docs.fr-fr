---
title: "CManualAccessor::CreateParameterAccessor | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CManualAccessor::CreateParameterAccessor"
  - "ATL.CManualAccessor.CreateParameterAccessor"
  - "CManualAccessor.CreateParameterAccessor"
  - "CreateParameterAccessor"
  - "CManualAccessor::CreateParameterAccessor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateParameterAccessor (méthode)"
ms.assetid: d0a2095b-b37c-4472-accc-45ef365a18c8
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CManualAccessor::CreateParameterAccessor
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Attribue la mémoire pour les structures de paramètres liés et initialise paramètres des données des membres.  
  
## Syntaxe  
  
```  
  
      HRESULT CreateParameterAccessor(   
   int nBindEntries,   
   void* pBuffer,   
   DBLENGTH nBufferSize    
) throw( );  
```  
  
#### Paramètres  
 `nBindEntries`  
 \<nombre de colonnes\>  
  
 `pBuffer`  
 \[in\] Un pointeur vers la mémoire tampon dans laquelle les colonnes d'entrée sont stockées.  
  
 `nBufferSize`  
 \[in\] Taille de la mémoire tampon en octets.  
  
## Valeur de retour  
 Une des valeurs standard `HRESULT`.  
  
## Notes  
 Vous devez appeler cette fonction avant d'appeler [Ajout des paramètres d'entrée](../../data/oledb/cmanualaccessor-addparameterentry.md).  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CManualAccessor, classe](../../data/oledb/cmanualaccessor-class.md)   
 [CManualAccessor::CreateAccessor](../../data/oledb/cmanualaccessor-createaccessor.md)   
 [CManualAccessor::AddParameterEntry](../../data/oledb/cmanualaccessor-addparameterentry.md)