---
title: processus | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: process_cpp
dev_langs: C++
helpviewer_keywords:
- __declspec keyword [C++], process
- process __declspec keyword
ms.assetid: 60eecc2f-4eef-4567-b9db-aaed34733023
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6754adcb348cb6eb061e32fc58e78f43663b1a90
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="process"></a>process
Spécifie que votre processus d'application managé doit comporter une seule copie d'une variable globale particulière, d'une variable membre static ou d'une variable locale static partagée par tous les domaines d'application du processus. Cela est principalement destiné à être utilisé lors de la compilation avec **/CLR : pure**, car sous **/CLR : pure** variables globales et static sont par domaine d’application par défaut. Les options de compilateur **/clr:pure** et **/clr:safe** sont dépréciées dans Visual Studio 2015. Lors de la compilation avec **/CLR**, les variables globales et static sont par processus par défaut (n’avez pas besoin d’utiliser `__declspec(process)`.  
  
 Seules une variable globale, une variable membre static ou une variable locale static de type natif peuvent être marquées avec `__declspec(process)`.  
  
 Lors de la compilation avec **/CLR : pure**, variables marquées par processus doivent également être déclarées comme `const`. Cela garantit que les variables par processus ne sont pas modifiées dans un domaine d'application et qu'elle n'entraînent pas de résultats inattendus dans un autre domaine d'application. Utilisation de la principale prévue `__declspec(process)` consiste à activer l’initialisation de temps de compilation d’une variable globale, une variable membre static ou une variable locale static sous **/CLR : pure**.  
  
 `process`est valide uniquement lors de la compilation avec [/CLR](../build/reference/clr-common-language-runtime-compilation.md) ou **/CLR : pure** et n’est pas valide lors de la compilation avec **/CLR : safe**.  
  
 Si vous souhaitez que chaque domaine d’application possède sa propre copie d’une variable globale, utilisez [appdomain](../cpp/appdomain.md).  
  
 Consultez [domaines d’Application et Visual C++](../dotnet/application-domains-and-visual-cpp.md) pour plus d’informations.  
  
## <a name="see-also"></a>Voir aussi  
 [__declspec](../cpp/declspec.md)   
 [Mots clés](../cpp/keywords-cpp.md)