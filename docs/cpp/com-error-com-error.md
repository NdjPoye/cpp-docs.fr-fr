---
title: "_com_error::_com_error | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_com_error._com_error"
  - "_com_error::_com_error"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_com_error (méthode)"
ms.assetid: 0a69e46c-caab-49ef-b091-eee401253ce6
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _com_error::_com_error
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Construit un objet `_com_error`.  
  
## Syntaxe  
  
```  
  
      _com_error(  
   HRESULT hr,  
   IErrorInfo* perrinfo = NULL,  
   bool fAddRef=false  
) throw( );  
_com_error(  
   const _com_error& that   
) throw( );  
```  
  
#### Paramètres  
 `hr`  
 Informations `HRESULT`.  
  
 `perrinfo`  
 Objet**IErrorInfo**.  
  
 **bool fAddRef\=false**  
 Entraîne l'appel par le constructeur d'AddRef sur une interface **IErrorInfo** non null.  Cela permet un décompte de références correct dans le cas fréquent où la propriété de l'interface est passée dans l'objet `_com_error`, comme suit :  
  
```  
throw _com_error(hr, perrinfo);  
```  
  
 Si vous ne souhaitez pas que votre code transfère la propriété à l'objet `_com_error`, et si `AddRef` est requis pour décaler **Release** dans le destructeur `_com_error`, construisez l'objet comme suit :  
  
```  
_com_error err(hr, perrinfo, true);  
```  
  
 `that`  
 Objet `_com_error` existant.  
  
## Notes  
 Le premier constructeur crée un nouvel objet à partir d'un objet `HRESULT` et d'un objet facultatif **IErrorInfo**.  Le deuxième constructeur crée une copie d'un objet `_com_error` existant.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [\_com\_error, classe](../cpp/com-error-class.md)