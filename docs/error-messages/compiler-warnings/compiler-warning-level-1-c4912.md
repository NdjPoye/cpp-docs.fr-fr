---
title: "Avertissement du compilateur (niveau&#160;1) C4912 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4912"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4912"
ms.assetid: ba1f1a66-8c20-4792-9ac8-43e49f729ae2
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau&#160;1) C4912
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'attribute' : comportement indéfini de l’attribut sur un UDT imbriqué  
  
 Les attributs qui s’appliquent aux UDT imbriqués \(type défini par l’utilisateur : typedef, union ou struct\) peuvent être ignorés.  
  
 Le code suivant montre comment cet avertissement est généré :  
  
```  
// C4912.cpp // compile with: /W1 #include <windows.h> [emitidl, module(name="xx")]; [object, uuid("00000000-0000-0000-0000-000000000002")] __interface IMy { }; [coclass, default(IMy), appobject, uuid("00000000-0000-0000-0000-000000000001")] class CMy : public IMy { [export, v1_enum] typedef enum myEnum { k3_1 = 1, k3_2 = 2 } myEnumv;   // C4912 }; int main() { }  
```