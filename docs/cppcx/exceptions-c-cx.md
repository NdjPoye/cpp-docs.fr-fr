---
title: Exceptions (C + c++ / CX) | Documents Microsoft
ms.custom: 
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6cbdc1f1-e4d7-4707-a670-86365146432f
caps.latest.revision: "22"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: b9b7a5af4816ff638918ccf7478465fe120e8e67
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="exceptions-ccx"></a>Exceptions (C++/CX)

Gestion des erreurs dans le langage c++ / CX est basée sur les exceptions. Au niveau plus fondamental, les composants Windows Runtime signalent les erreurs en tant que valeurs HRESULT. Dans C + c++ / CX, ces valeurs sont converties en exceptions fortement typées qui contiennent une valeur HRESULT et une description de la chaîne que vous pouvez accéder par programme.  Les exceptions sont implémentées sous forme de `ref class` qui dérive de `Platform::Exception`.  L'espace de noms `Platform` définit des classes d'exception distinctes pour les valeurs HRESULT les plus courantes. Toutes les autres valeurs sont indiquées via la classe `Platform::COMException` . Toutes les classes d'exceptions ont un champ de [Exception::HResult](platform-exception-class.md#hresult) qui peut être utilisé pour récupérer le HRESULT d'origine. Vous pouvez également consulter les informations de pile des appels pour le code utilisateur dans le débogueur peut aider à identifier la source d’origine de l’exception, même si celle-ci provient du code qui a été écrite dans un autre langage que C++.  
  
## <a name="exceptions"></a>Exceptions  
 Dans votre programme C++, vous pouvez lever et intercepter une exception qui provient d’une opération de Windows Runtime, une exception qui est dérivée de `std::exception`, ou un type défini par l’utilisateur. Vous devez lever une exception de Windows Runtime uniquement lorsqu’elle traversera la limite (ABI) de l’interface binaire d’application, par exemple, lorsque le code qui intercepte votre exception est écrit en JavaScript. Lorsqu’une exception de Windows Runtime C++ atteint la limite ABI, elle est convertie en un `Platform::FailureException` exception, ce qui représente un HRESULT E_FAIL. Pour plus d'informations sur l'ABI, consultez [Creating Windows Runtime Components in C++](/MicrosoftDocs/windows-uwp/blob/docs/windows-apps-src/winrt-components/creating-windows-runtime-components-in-cpp.md).  
  
 Vous pouvez déclarer [Platform::Exception](platform-exception-class.md) à l'aide de l'un des deux constructeurs qui acceptent soit un paramètre HRESULT, soit un paramètre HRESULT et un paramètre [Platform::String](platform-string-class.md)^ pouvant être passé via ABI à une application Windows Store qui le prend en charge. Vous pouvez aussi déclarer une exception à l'aide de l'une des deux surcharges de méthode [Exception::CreateException](platform-exception-class.md#createexception) qui acceptent un paramètre HRESULT ou un paramètre HRESULT et un paramètre `Platform::String^` .  
  
## <a name="standard-exceptions"></a>Exceptions standard  
 C + c++ / CX prend en charge un ensemble d’exceptions standard qui représentent les erreurs HRESULT courantes. Chaque exception standard dérive de [Platform::COMException](platform-comexception-class.md), qui dérive à son tour de `Platform::Exception`. Lorsque vous levez une exception à travers la limite ABI, vous devez lever l'une des exceptions standard.  

 Vous ne pouvez pas dériver votre propre type d'exception de `Platform::Exception`. Pour lever une exception personnalisée, utilisez un HRESULT défini par l'utilisateur pour construire un objet `COMException` .  
  
 Le tableau ci-dessous répertorie les exceptions standard.  
  
|Nom|HRESULT sous-jacent|Description|  
|----------|------------------------|-----------------|  
|COMException|*hresult défini par l’utilisateur*|Levée lorsqu'un HRESULT non reconnu est retourné d'un appel de méthode COM.|  
|AccessDeniedException|E_ACCESSDENIED|Levée lorsque l'accès est refusé à une ressource ou à une fonctionnalité.|  
|ChangedStateException|E_CHANGED_STATE|Levée lorsque les méthodes d'un itérateur de collection ou d'une vue de collection sont appelées après la modification d'une collection parente, invalidant ainsi les résultats de la méthode.|  
|ClassNotRegisteredException|REGDB_E_CLASSNOTREG|Levée lorsqu'une classe COM n'a pas été inscrite.|  
|DisconnectedException|RPC_E_DISCONNECTED|Levée lorsqu'un objet est déconnecté de ses clients.|  
|FailureException|E_FAIL|Levée lorsqu'une opération échoue.|  
|InvalidArgumentException|E_INVALIDARG|Levée lorsque l'un des arguments fournis à une méthode n'est pas valide.|  
|InvalidCastException|E_NOINTERFACE|Levée lorsqu'un type ne peut pas être casté en un autre type.|  
|NotImplementedException|E_NOTIMPL|Levée si une méthode d'interface n'a pas été implémentée pour une classe.|  
|NullReferenceException|E_POINTER|Levée lors d'une tentative de suppression de la référence à une référence d'objet null.|  
|ObjectDisposedException|RO_E_CLOSED|Levée lorsqu'une opération est exécutée sur un objet supprimé.|  
|OperationCanceledException|E_ABORT|Levée lorsqu'une opération est abandonnée.|  
|OutOfBoundsException|E_BOUNDS|Levée lorsqu'une opération tente d'accéder aux données en dehors de la plage valide.|  
|OutOfMemoryException|E_OUTOFMEMORY|Levée en cas de mémoire insuffisante pour terminer l'opération.|  
|WrongThreadException|RPC_E_WRONG_THREAD|Levée lorsqu'un thread effectue un appel via un pointeur d'interface qui concerne un objet proxy qui n'appartient pas à l'apartment du thread.|  
  
## <a name="hresult-and-message-properties"></a>Propriétés HRESULT et Message  
 Toutes les exceptions ont une propriété [HRESULT](platform-comexception-class.md#hresult) et une propriété [Message](platform-comexception-class.md#message) . La propriété [Exception::HResult](platform-exception-class.md#hresult) obtient la valeur HRESULT numérique sous-jacente de l'exception. La propriété [Exception::Message](platform-exception-class.md#message) obtient la chaîne fournie par le système qui décrit l'exception. Dans Windows 8, le message est disponible uniquement dans le débogueur et est en lecture seule. Cela signifie que vous ne pouvez pas le modifier quand vous levez de nouveau l'exception. Dans Windows 8.1, vous pouvez accéder à la chaîne de message par programmation et fournir un nouveau message si vous levez de nouveau l'exception. Des informations plus riches relatives aux piles des appels sont également disponibles dans le débogueur, notamment les piles des appels correspondant aux appels de méthode asynchrones.  
  
### <a name="examples"></a>Exemples  
 Cet exemple montre comment lever une exception d’exécution de Windows pour les opérations synchrones :  
  
 [!code-cpp[cx_exceptions#01](codesnippet/CPP/exceptiontest/class1.cpp#01)]  
  
 L'exemple ci-dessous montre comment intercepter l'exception.  
  
 [!code-cpp[cx_exceptions#02](codesnippet/CPP/exceptiontest/class1.cpp#02)]  
  
 Pour intercepter les exceptions levées pendant une opération asynchrone, utilisez la classe de tâche et ajoutez une continuation de gestion des erreurs. La continuation de gestion des erreurs marshale les exceptions levées sur d'autres threads vers le thread appelant afin de gérer toutes les exceptions éventuelles en un seul point de votre code. Pour plus d’informations sur la programmation asynchrone, consultez [Programmation asynchrone en C++](http://msdn.microsoft.com/library/windows/apps/Hh780559.aspx).  
  
## <a name="unhandlederrordetected-event"></a>Événement UnhandledErrorDetected  
 Dans Windows 8.1 vous pouvez vous abonner à la [unhandlederrordetected](http://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.core.coreapplication.unhandlederrordetected.aspx) événement statique, ce qui permet d’accéder aux erreurs non gérées qui sont sur le point d’interrompre le processus. Indépendamment de l’origine de l’erreur, il atteint ce gestionnaire en tant qu’objet [Windows::ApplicationModel::Core::UnhandledError](http://msdnstage.redmond.corp.microsoft.com/library/windows/apps/windows.applicationmodel.core.unhandlederror.aspx) passé avec les arguments d’événement. Lorsque vous appelez `Propagate` sur l'objet, il crée et lève une exception `Platform::*Exception` dont le type correspond au code d'erreur. Dans les blocs catch, vous pouvez enregistrer l'état utilisateur, le cas échéant. Vous pouvez ensuite permettre au processus de se terminer en appelant `throw`, ou vous pouvez faire en sorte de restaurer le programme à un état connu. L'exemple suivant illustre le modèle de base :  
  
```  
  
// In app.xaml.h:  
void OnUnhandledException(Platform::Object^ sender, Windows::ApplicationModel::Core::UnhandledErrorDetectedEventArgs^ e);  
  
// In app.xaml.cpp  
  
// Subscribe to the event, for example in the app class constructor:  
Windows::ApplicationModel::Core::CoreApplication::UnhandledErrorDetected += ref new EventHandler<UnhandledErrorDetectedEventArgs^>(this, &App::OnUnhandledException);  
  
// Event handler implementation:  
void App::OnUnhandledException(Platform::Object^ sender, Windows::ApplicationModel::Core::UnhandledErrorDetectedEventArgs^ e)  
{  
    auto err = e->UnhandledError;  
  
    if (!err->Handled) //Propagate has not been called on it yet.  
{  
     try  
    {  
        err->Propagate();  
    }  
    // Catch any specific exception types if you know how to handle them  
    catch (AccessDeniedException^ ex)  
    {  
        // TODO: Log error and either take action to recover  
        // or else re-throw exception to continue fail-fast  
    }  
  
}  
  
```  
  
### <a name="remarks"></a>Remarques  
 C + c++ / CX n’utilise pas le `finally` clause.  
  
## <a name="see-also"></a>Voir aussi  
 [Référence du langage Visual C++](visual-c-language-reference-c-cx.md)   
 [Référence des espaces de noms](namespaces-reference-c-cx.md)