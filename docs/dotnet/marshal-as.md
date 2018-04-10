---
title: marshal_as | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- marshal_as
- msclr.interop.marshal_as
- msclr::interop::marshal_as
dev_langs:
- C++
helpviewer_keywords:
- marshal_as template [C++]
ms.assetid: 2ed717da-2b11-41e5-981d-47d251771989
caps.latest.revision: 17
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 1a209b1ee657d6ae6773ee88c64225a7dc5b4f49
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="marshalas"></a>marshal_as
Cette méthode convertit les données entre les environnements natifs et managés.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
To_Type marshal_as<To_Type>(  
   From_Type input   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 [in] `input`  
 La valeur que vous souhaitez marshaler un `To_Type` variable.  
  
## <a name="return-value"></a>Valeur de retour  
 Une variable de type `To_Type` qui est la valeur convertie de `input`.  
  
## <a name="remarks"></a>Notes  
 Cette méthode est une méthode simplifiée pour convertir des données entre les types managés et natifs. Pour déterminer quels types de données sont pris en charge, consultez [vue d’ensemble du Marshaling dans C++](../dotnet/overview-of-marshaling-in-cpp.md). Certaines conversions de données nécessitent un contexte. Vous pouvez convertir ces types de données à l’aide de la [marshal_context, classe](../dotnet/marshal-context-class.md).  
  
 Si vous tentez de marshaler une paire de types de données qui ne sont pas pris en charge, `marshal_as` génère une erreur [C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md) au moment de la compilation. Lisez le message fourni avec cette erreur pour plus d’informations. Le `C4996` erreur peut être générée pour les fonctions plus simplement déconseillées. Un exemple tente de marshaler une paire de types de données qui ne sont pas pris en charge.  
  
 La bibliothèque de marshaling se compose de plusieurs fichiers d’en-tête. Toute conversion ne nécessite qu’un seul fichier, mais vous pouvez inclure des fichiers supplémentaires si vous avez besoin pour les autres conversions. Pour voir quelles conversions sont associées à des fichiers, regardez dans la table `Marshaling Overview`. La spécification de l’espace de noms, de quelle conversion vous souhaitez effectuer, est toujours en vigueur.  
  
## <a name="example"></a>Exemple  
 Cet exemple marshale à partir d’un `const char*` à un `System::String` le type de variable.  
  
```  
// marshal_as_test.cpp  
// compile with: /clr  
#include <stdlib.h>  
#include <string.h>  
#include <msclr\marshal.h>  
  
using namespace System;  
using namespace msclr::interop;  
  
int main() {  
   const char* message = "Test String to Marshal";  
   String^ result;  
   result = marshal_as<String^>( message );  
   return 0;  
}  
```  
  
## <a name="requirements"></a>Configuration requise  
 **Fichier d’en-tête :** \<msclr\marshal.h >, \<msclr\marshal_windows.h >, \<msclr\marshal_cppstd.h >, ou \<msclr\marshal_atl.h >  
  
 **Namespace :** msclr::interop  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble du Marshaling dans C++](../dotnet/overview-of-marshaling-in-cpp.md)   
 [marshal_context Class](../dotnet/marshal-context-class.md)