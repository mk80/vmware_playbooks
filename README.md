# vmware_playbooks

Playbooks to use with vcenter. For example:
Deploy VMs from templates, add disks to VMs, rename VMs, migrate VM datastore, upgrade vmware tools on VM, query datacenter... and whatever else you can come up with!

This requires a host that has ansible installed with required packages.

The add_network playbook will work once next version of ansible is release, 2.9

Populate group_vars/vars.yaml with required data for each variable and then run the playbook.

Variable explanations:

	Variable:						Example:
		vcenter_hostname			vcenter fqdn
		vcenter_username			account
		vcenter_password			account password
		datacenter					name in vsphere
		cluster						name in vsphere
		datastore					name in vsphere
		destination_datastore		Different datastore for migration
		network				network to attach first interface
		network_2			second network interface
		template			name of template stored in vsphere
		vm_name				hostname of VM as seen in vcenter
		uuid				4205c5df-ce7d-653d-bf7c-df72023110fc
		disk_size			size in GB
		unit_number			unit number on first scsi controller (sequential for each disk; greater than 0)
		memory				size in MB
		cpu 				number of CPUs
	
Variables needed for each playbook:

	add_disks.yaml:        '{{ vcenter_hostname }}'
	add_disks.yaml:        '{{ vcenter_username }}'
	add_disks.yaml:        '{{ vcenter_password }}'
	add_disks.yaml:        '{{ datacenter }}'
	add_disks.yaml:        '{{ uuid }}'
	add_disks.yaml:        '{{ disk_size }}'
	add_disks.yaml:        '{{ datastore }}'
	add_disks.yaml:        '{{ unit_number }}'

	add_network.yaml:        '{{ vcenter_hostname }}'
	add_network.yaml:        '{{ vcenter_username }}'
	add_network.yaml:        '{{ vcenter_password }}'
	add_network.yaml:        '{{ datacenter }}'
	add_network.yaml:        '{{ uuid }}'
	add_network.yaml:        '{{ network_2 }}'

	create_vm_with_template.yaml:        '{{ vcenter_hostname }}'
	create_vm_with_template.yaml:        '{{ vcenter_username }}'
	create_vm_with_template.yaml:        '{{ vcenter_password }}'
	create_vm_with_template.yaml:        '{{ cluster }}'
	create_vm_with_template.yaml:        '{{ vm_name }}'
	create_vm_with_template.yaml:        '{{ template }}'
	create_vm_with_template.yaml:        '{{ datastore }}'
	create_vm_with_template.yaml:        '{{ memory }}'
	create_vm_with_template.yaml:        '{{ cpu }}'
	create_vm_with_template.yaml:        '{{ network }}'

	get_vm_full_info.yaml:        '{{ vcenter_hostname }}'
	get_vm_full_info.yaml:        '{{ vcenter_username }}'
	get_vm_full_info.yaml:        '{{ vcenter_password }}'
	get_vm_full_info.yaml:        '{{ datacenter }}'
	get_vm_full_info.yaml:        '{{ uuid }}'

	get_vm_uuid.yaml:        '{{ vcenter_hostname }}'
	get_vm_uuid.yaml:        '{{ vcenter_username }}'
	get_vm_uuid.yaml:        '{{ vcenter_password }}'
	get_vm_uuid.yaml:        '{{ datacenter }}'
	get_vm_uuid.yaml:        '{{ vm_name }}'

	migrate_datastore.yaml:        '{{ vcenter_hostname }}'
	migrate_datastore.yaml:        '{{ vcenter_username }}'
	migrate_datastore.yaml:        '{{ vcenter_password }}'
	migrate_datastore.yaml:        '{{ uuid }}'
	migrate_datastore.yaml:        '{{ destination_datastore }}'

	rename_vm.yaml:        '{{ vcenter_hostname }}'
	rename_vm.yaml:        '{{ vcenter_username }}'
	rename_vm.yaml:        '{{ vcenter_password }}'
	rename_vm.yaml:        '{{ uuid }}'
	rename_vm.yaml:        '{{ new_name }}'

	tools_upgrade.yaml:        '{{ vcenter_hostname }}'
	tools_upgrade.yaml:        '{{ vcenter_username }}'
	tools_upgrade.yaml:        '{{ vcenter_password }}'
	tools_upgrade.yaml:        '{{ datacenter }}'
	tools_upgrade.yaml:        '{{ uuid }}'
