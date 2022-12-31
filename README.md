 <h1><p align="center">Gpac</p></h1>
<p align="center"><img src="https://user-images.githubusercontent.com/120978605/210135754-05ed3664-e32b-4bf3-b1b3-20b61311c6a3.png" width="400" /></p>


>* <h4>linux-hardened</h4>
>
>- <h4>hardened_malloc</h4>
>
>+ <h4>virt-manager</h4>
>
>* <h4>sysctl tweaks</h4>
>
>- <h4>encrypted persistence</h4>
>
>+ <h4>USBKill</h4>
>  + Демон при изменении в списке USB устройств выключает ПК и чистит оперативную память.
>
>* <h4>USBGuard</h4>
>  * Демон фильтрации недоверенных устройств на основе белого списка.
>- <h4>OpenSnitch</h4>
>  - App Firewall.


* <h3>От автора</h3>
>- За основу взяты твики из [Obscurix](https://obscurix.github.io/security/overview.html).  
>- Система оптимизирована для работы в RAM, требуется 16гб для комфортной работы.  
>- Так же хочу заметить, что собрав ее и установив на флешку, вы можете использовать этот образ в virt-manager, как замену Whonix Worstation.  
>- Для сборки слегка модифицирован прекрасный проект [Archuseriso](https://github.com/laurent85v/archuseriso). 
>Понадобится Arch-система или желание её установить. [RU](https://telegra.ph/1-Ustanovka-Arch-Linux-12-28)|[ENG](https://telegra.ph/1-Arch-Linux-Installation-12-28)

## Сборка и запись образа

Для сборки iso выполните следующие команды:
```
git clone https://github.com/PacSec/Gpac
cd Gpac
sudo ./aui-mkiso ./profile -l ru -v
```

Для записи на flash-накопитель с encrypted persistence выполните:
```
sudo ./aui-mkusb --size-esp=1G --size-cow=12G --ext4-no-journal --encrypt out/Gpac.iso /dev/sdX
```
Где `/dev/sdX` — ваша флешка, полученная из `lsblk`.

*Если носитель размером 16Gb, то под persistence вы можете выделить только 16-1-2.5=12Gb.*

## USBGuard и USBKill

Для генерации списка доверенных USB-устройств, подключите их к вашему ПК и выполните в терминале:
```
sudo usbregen
```

Для включения `USBKill` выполните:
```
sudo usbkillon
```
Демон ожидает отключение или подключение какого-либо устройства, при обнаружении которого он выключит систему для предотвращения неправомерного доступа.

Если же вам нужно поработать с каким-либо устройством, выполните:
```
sudo usbkilloff
```
А потом снова включите:
```
sudo usbkillon
```

## yay

Если вам понадобится yay:
```
sudo get_yay
```

## Whonix

Если вам вдруг понадобится Whonix, то вы легко его сможете установить, выполнив команду в терминале:
```
sudo get_whonix
```

## Приятной работы!

В следующей версии вас ждет новая тема оформления, центр управления, а также множество мелочей, направленных на повышение безопасности системы.
##
От ваших донатов зависит скорость развития данного проекта.

##### XMR
```
427RHsYcgCs6p5NUhB6WYdeNPWAV9CGWFL8JtYnWEeS551WMEZLvnYaPNK6ATp8LGWYE1pHxwQ4kLEhc2uGkgWaEABb8qNo
```
##### BTC
```
bc1qww8023kcryqt84gvleuhmv6dtln599ccp0pggr
```
