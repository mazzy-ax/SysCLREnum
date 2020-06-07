# SysCLREnum

[project]:https://github.com/mazzy-ax/SysCLREnum
[license]:https://github.com/mazzy-ax/SysCLREnum/blob/master/LICENSE
[System.Enum]:https://docs.microsoft.com/en-us/dotnet/api/system.enum

[SysCLREnum][project] &ndash; это класс-обертка на языке X++ для работы перечислениями .net ([System.Enum]) в [Microsoft Dynamics AX 2009](ax2009), [Microsoft Dynamics AX 2012](ax2012) и [Axapta 4.0](ax4).

## Отличия для ax4 и ax2009, 2012

* В `ax2012` в методе `equal` для проверки на класс `SysCLREnum` используется оператор `is` вместо устаревшего (obsolete) метода `SysDictClass::is()`. Однако для проверки на класс `CRLObject` пока используется устаревший метод.
* В `ax4` вместо литералов вида `System.TypeCode::int32` используется метод `CLRInterop::parseClrEnum('System.TypeCode','int32')`.
* В `ax4` вместо `System.Enum` используется `System.Object` поскольку `ax4` не умеет автоматически кастовать `CRLObject`, возвращаемый из метода.

## Известные проблемы

1. Класс в данной версии работает с перечислениями, для которых базовым типом является `int32` и уже, и не может работать с перечислениями, для которых базовым типом является `int64`. см. метод [GetTypeCode](https://docs.microsoft.com/en-us/dotnet/api/system.enum.gettypecode).
2. Класс в данной версии не понимает объединение значений-флагов и не предоставляет функционал для работы с объединениями. см. метод [HasFlag](https://docs.microsoft.com/ru-ru/dotnet/api/system.enum.hasflag).

## ChangeLog

* [CHANGELOG.md](CHANGELOG.md)
* <https://github.com/mazzy-ax/SysCLREnum/releases>

## Помощь проекту

Буду признателен за ваши замечания, предложения и советы по проекту как в разделе [Issues](https://github.com/mazzy-ax/SysCLREnum/issues), так и в виде письма на адрес <mazzy@mazzy.ru>

Мазуркин Сергей (mazzy)
