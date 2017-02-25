---
title: "_com_raise_error, fonction | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_com_raise_error"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_com_raise_error (fonction)"
ms.assetid: a98226c2-c3fe-44f1-8ff5-85863de11cd6
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# _com_raise_error, fonction
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Lève [\_com\_error](../cpp/com-error-class.md) en réponse à un échec.  
  
## Syntaxe  
  
```  
  
      void __stdcall _com_raise_error(  
   HRESULT hr,  
   IErrorInfo* perrinfo = 0  
);  
```  
  
#### Paramètres  
 `hr`  
 Informations `HRESULT`.  
  
 `perrinfo`  
 Objet**IErrorInfo**.  
  
## Notes  
 `_com_raise_error`, définie dans comdef.h, peut être remplacée par une version de même nom et prototype écrite par l'utilisateur.  Cette opération peut être effectuée si vous souhaitez utiliser `#import` mais pas la gestion des exceptions C\+\+.  Dans ce cas, une version utilisateur de **\_com\_raise\_error** pourrait déterminer l'exécution d'un `longjmp` ou l'affichage d'un message et une interruption.  Toutefois, cette version utilisateur ne devrait pas être retournée, car le code de prise en charge COM du compilateur n'attend aucun retour de celle\-ci.  
  
 Vous pouvez également utiliser [\_set\_com\_error\_handler](../cpp/set-com-error-handler.md) pour remplacer la fonction par défaut de gestion des erreurs.  
  
 Par défaut, `_com_raise_error` est défini comme suit :  
  
```  
void __stdcall _com_raise_error(HRESULT hr, IErrorInfo* perrinfo) {  
   throw _com_error(hr, perrinfo);  
}  
```  
  
## FIN de la section spécifique à Microsoft  
  
## Configuration requise  
 **En\-tête :** comdef.h  
  
 **Lib :**si l'option de compilateur « wchar\_t est le type natif » est activée, utilisez comsuppw.lib ou le comsuppwd.lib.  Si l'option « wchar\_t est le type natif » est désactivée, utilisez comsupp.lib.  Pour plus d'informations, consultez [\/Zc:wchar\_t \(wchar\_t est un type natif\)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md).  
  
## Voir aussi  
 [Fonctions globales COM du compilateur](../cpp/compiler-com-global-functions.md)   
 [\_set\_com\_error\_handler](../cpp/set-com-error-handler.md)