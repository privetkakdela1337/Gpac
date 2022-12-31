# Gpac

При старте OS вам доступна система виртуализации `qemu-kvm` и её фронт в виде `virt-manager`. Интегрирован демон `usbkill`, который при изменении состояния USB выключает ПК и `usbguard`, пускающий только доверенные устройства. Есть firewall [OpenSnitch](https://github.com/evilsocket/opensnitch).

За основу взяты твики из [Obscurix](https://obscurix.github.io/security/overview.html). Для сборки слегка модифицирован прекрасный проект [Archuseriso](https://github.com/laurent85v/archuseriso).

Понадобится Arch-система или желание её установить. [RU](https://telegra.ph/1-Ustanovka-Arch-Linux-12-28)|[ENG](https://telegra.ph/1-Arch-Linux-Installation-12-28)

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

## Usbguard и usbkill

Для генерации списка доверенных USB-устройств, подключите их к вашему ПК и выполните в терминале:
```
sudo usbregen
```

Для включения `usbkill` выполните:
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
