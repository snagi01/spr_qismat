
Data analysis is done in SC at /nfs/sc/disks/sdg74_3328/PycharmProjects/spr_qismat/
```
setenv PATH /nfs/sc/disks/sdg74_3328/pycharm-env/bin:$PATH
setenv PATH /nfs/sc/disks/sdg74_3328/PycharmProjects/spr_qismat/scripts/:$PATH

cd stats_19ww06
# in design environment:
blocks_info.pl -csv ',' -headers template,name,physical_parent,type,release,chops,sub_ip -sortby template > blocks_info_19ww06.csv
findallnetlists.sh
pull_sch_from_blocks_info.pl spr_blocks_info_19ww06.txt sch_list_sorted.txt > blocks_info_19ww06_with_sch.txt
cd ..
# edit the output filename: 
vi blocks_info_to_arch_rollup.py
../../pycharm-env/bin/python blocks_info_to_arch_rollup.py
# the output of this can be used as an input to the QISMAT script
```