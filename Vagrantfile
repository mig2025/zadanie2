MACHINES={
  ## Указываем имя ВМ "kernel update"
  :"kernel-update"=>{
     :box_name=>"generic/centos8s",
    #Указываем box_version
     :box_version=>"4.3.4",
     #Указываем количество ядер ВМ
      :cups=>2
  }
}

Vagrant.configure("2") do |config|
  MACHINES.each do |boxname, boxconfig|
    # Отключаем проброс общей папки в ВМ
    config.vm.synced_folder ".", "/vagrant", disabled: true
    # Применяем конфигурацию ВМ
    config.vm.define boxname do |box|
      box.vm.box = boxconfig[:box_name]
      box.vm.box_version = boxconfig[:box_version]
      box.vm.host_name = boxname.to_s
   end
 end
end