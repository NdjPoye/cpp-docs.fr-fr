---
title: "Exception::Message (propri&#233;t&#233;) | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Exception::Message"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Exception::Message (propriété)"
ms.assetid: ad1199cd-0889-4803-ad0d-a3a7b3c51891
caps.latest.revision: 10
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Exception::Message (propri&#233;t&#233;)
Message qui décrit l'erreur.  
  
## Syntaxe  
  
```cpp  
public:property String^ Message;  
```  
  
## Valeur de propriété  
 Dans les exceptions qui proviennent de Windows Runtime, il s'agit d'une description de l'erreur fournie par le système.  
  
## Notes  
 Dans [!INCLUDE[win8](../cppcx/includes/win8-md.md)], cette propriété est en lecture seule, car les exceptions dans cette version de Windows Runtime traversent ABI uniquement sous forme de HRESULTS. Dans [!INCLUDE[win81](../cppcx/includes/win81-md.md)], les informations sur l'exception traversent l'ABI. Par ailleurs, vous pouvez fournir un message personnalisé accessible par programmation à d'autres composants. Pour plus d'informations, consultez [Exceptions \(C\+\+\/CX\)](../cppcx/exceptions-c-cx.md).  
  
## Configuration requise  
 **Client minimum pris en charge :** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Serveur minimum pris en charge :** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Espace de noms :** Platform  
  
 **Métadonnées :** platform.winmd  
  
## Voir aussi  
 [Platform::Exception \(classe\)](../cppcx/platform-exception-class.md)