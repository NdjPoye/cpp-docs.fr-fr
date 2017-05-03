---
title: "Int&#233;gration&#160;WRL (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "01/22/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3ad43894-c574-477c-ad3e-240301f381d4
caps.latest.revision: 9
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 9
---
# Int&#233;gration&#160;WRL (C++/CX)
Vous pouvez mélanger librement le code [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] et le code [!INCLUDE[cppwrl](../cppcx/includes/cppwrl-md.md)] \([!INCLUDE[cppwrl_short](../cppcx/includes/cppwrl-short-md.md)]\). Dans la même unité de traduction, vous pouvez utiliser des objets déclarés avec la notation [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] handle\-to\-object \(`^`\) et la notation du pointeur intelligent [!INCLUDE[cppwrl_short](../cppcx/includes/cppwrl-short-md.md)] \(`ComPtr<T>`\). Toutefois, vous devez gérer manuellement les valeurs de retour, ainsi que les codes d'erreur HRESULT [!INCLUDE[cppwrl_short](../cppcx/includes/cppwrl-short-md.md)] et les exceptions [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)].  
  
## Développement [!INCLUDE[cppwrl_short](../cppcx/includes/cppwrl-short-md.md)]  
 Pour plus d'informations sur la conception et la consommation des composants [!INCLUDE[cppwrl_short](../cppcx/includes/cppwrl-short-md.md)], consultez [Bibliothèque de modèles Windows Runtime C\+\+ \(WRL\)](~/windows/windows-runtime-cpp-template-library-wrl.md).  
  
## Exemple  
 L'extrait de code suivant illustre l'utilisation de [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] et [!INCLUDE[cppwrl_short](../cppcx/includes/cppwrl-short-md.md)] pour utiliser des classes [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] et examiner un fichier de métadonnées.  
  
 Exemple tiré d’un extrait de code du [forum sur la création d’applications du Windows Store](http://social.msdn.microsoft.com/Forums/winappswithnativecode/thread/211ef583-db11-4e55-926b-6d9ab53dbdb4). L'auteur de cet extrait de code offre les exclusions et les conditions suivantes :  
  
1.  C\+\+ ne fournit pas les API spécifiques à réfléchir sur les types [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)], mais les fichiers de métadonnées Windows \(.winmd\) pour un type sont totalement conformes aux fichiers de métadonnées CLR. Windows propose les nouvelles API de découverte des métadonnées \(RoGetMetaDataFile\) pour obtenir le fichier .winmd pour un type donné. Toutefois, l'utilisation de ces API est limitée aux développeurs C\+\+ car il est impossible d'instancier une classe.  
  
2.  Une fois le code compilé, vous devez également passer Runtimeobject.lib et Rometadata.lib à l'Éditeur de liens.  
  
3.  Cet extrait de code est présenté comme tel. Alors qu'il est censé fonctionner correctement, il peut éventuellement contenir des erreurs.  
  
```  
  
#include <hstring.h> #include <cor.h> #include <rometadata.h> #include <rometadataresolution.h> #include <collection.h> namespace ABI_Isolation_Workaround { #include <inspectable.h> #include <WeakReference.h> } using namespace ABI_Isolation_Workaround; #include <wrl/client.h> using namespace Microsoft::WRL; using namespace Windows::Foundation::Collections; IVector<String^>^ GetTypeMethods(Object^); MainPage::MainPage() { InitializeComponent(); Windows::Foundation::Uri^ uri = ref new Windows::Foundation::Uri("http://buildwindows.com/"); auto methods = GetTypeMethods(uri); std::wstring strMethods; std::for_each(begin(methods), end(methods), [&strMethods](../standard-library/string.md methodName) { strMethods += methodName->Data(); strMethods += L"\n"; }); wprintf_s(L"%s\n", strMethods.c_str()); } IVector<String^>^ GetTypeMethods(Object^ instance) { HRESULT hr; HSTRING hStringClassName; hr = instance->__cli_GetRuntimeClassName(reinterpret_cast<__cli_HSTRING__**>(&hStringClassName)); // internal method name subject to change post BUILD if (FAILED(hr)) __cli_WinRTThrowError(hr); // internal method name subject to change post BUILD String^ className = reinterpret_cast<String^>(hStringClassName); ComPtr<IMetaDataDispenserEx> metadataDispenser;ComPtr<IMetaDataImport2> metadataImport;hr = MetaDataGetDispenser(CLSID_CorMetaDataDispenser, IID_IMetaDataDispenser, (LPVOID*)metadataDispenser.GetAddressOf()); if (FAILED(hr)) __cli_WinRTThrowError(hr); // internal method name subject to change post BUILD HSTRING hStringFileName; mdTypeDef typeDefToken; hr = RoGetMetaDataFile(hStringClassName, metadataDispenser.Get(), &hStringFileName, &metadataImport, &typeDefToken); if (FAILED(hr)) __cli_WinRTThrowError(hr); // internal method name subject to change post BUILD String^ fileName = reinterpret_cast<String^>(hStringFileName); HCORENUM hCorEnum = 0; mdMethodDef methodDefs[2048]; ULONG countMethodDefs = sizeof(methodDefs); hr = metadataImport->EnumMethods(&hCorEnum, typeDefToken, methodDefs, countMethodDefs,  &countMethodDefs); if (FAILED(hr)) __cli_WinRTThrowError(hr); // internal method name subject to change post BUILD wchar_t methodName[1024]; ULONG countMethodName; std::wstring strMethods; Vector<String^>^ retVal = ref new Vector<String^>(); for(int i = 0; i < countMethodDefs; ++i) { countMethodName = sizeof(methodName); hr = metadataImport->GetMethodProps(methodDefs[i], nullptr, methodName, countMethodName, &countMethodName, nullptr, nullptr, nullptr, nullptr, nullptr); if (SUCCEEDED(hr)) { methodName[ countMethodName ] = 0; retVal->Append(ref new String(methodName)); } } return retVal; }  
  
```  
  
## Voir aussi  
 [Interopérabilité avec d'autres langages](../cppcx/interoperating-with-other-languages-c-cx.md)