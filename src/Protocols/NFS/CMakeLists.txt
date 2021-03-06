
########### next target ###############

SET(nfsproto_STAT_SRCS
   mnt_Dump.c
   mnt_Export.c
   mnt_Mnt.c
   mnt_Null.c
   mnt_Umnt.c
   mnt_UmntAll.c
   nfs_null.c
   nfs4_Compound.c
   nfs4_op_access.c
   nfs4_op_bind_conn.c
   nfs4_op_close.c
   nfs4_op_commit.c
   nfs4_op_create.c
   nfs4_op_create_session.c
   nfs4_op_delegpurge.c
   nfs4_op_delegreturn.c
   nfs4_op_destroy_session.c
   nfs4_op_exchange_id.c
   nfs4_op_free_stateid.c
   nfs4_op_getattr.c
   nfs4_op_getdeviceinfo.c
   nfs4_op_getdevicelist.c
   nfs4_op_getfh.c
   nfs4_op_illegal.c
   nfs4_op_layoutcommit.c
   nfs4_op_layoutget.c
   nfs4_op_layoutreturn.c
   nfs4_op_link.c
   nfs4_op_lock.c
   nfs4_op_lockt.c
   nfs4_op_locku.c
   nfs4_op_lookup.c
   nfs4_op_lookupp.c
   nfs4_op_nverify.c
   nfs4_op_open.c
   nfs4_op_open_confirm.c
   nfs4_op_open_downgrade.c
   nfs4_op_openattr.c
   nfs4_op_putfh.c
   nfs4_op_putpubfh.c
   nfs4_op_putrootfh.c
   nfs4_op_read.c
   nfs4_op_readdir.c
   nfs4_op_readlink.c
   nfs4_op_reclaim_complete.c
   nfs4_op_release_lockowner.c
   nfs4_op_remove.c
   nfs4_op_rename.c
   nfs4_op_renew.c
   nfs4_op_restorefh.c
   nfs4_op_savefh.c
   nfs4_op_secinfo.c
   nfs4_op_secinfo_no_name.c
   nfs4_op_sequence.c
   nfs4_op_set_ssv.c
   nfs4_op_setattr.c
   nfs4_op_xattr.c
   nfs4_op_setclientid.c
   nfs4_op_setclientid_confirm.c
   nfs4_op_destroy_clientid.c
   nfs4_op_test_stateid.c
   nfs4_op_verify.c
   nfs4_op_write.c
   nfs4_pseudo.c
   nfs_proto_tools.c
)

if(USE_NFS3)
  SET(nfsproto_STAT_SRCS
    ${nfsproto_STAT_SRCS}
    nfs3_access.c
    nfs3_commit.c
    nfs3_create.c
    nfs3_fsinfo.c
    nfs3_fsstat.c
    nfs3_getattr.c
    nfs3_link.c
    nfs3_lookup.c
    nfs3_mkdir.c
    nfs3_mknod.c
    nfs3_pathconf.c
    nfs3_read.c
    nfs3_readdir.c
    nfs3_readdirplus.c
    nfs3_readlink.c
    nfs3_remove.c
    nfs3_rename.c
    nfs3_rmdir.c
    nfs3_setattr.c
    nfs3_symlink.c
    nfs3_write.c
    )
endif(USE_NFS3)

add_library(nfsproto STATIC ${nfsproto_STAT_SRCS})
add_sanitizers(nfsproto)

set(nfs4callbackSRCS
   nfs4_cb_Compound.c
)

add_library(nfs4callbacks STATIC ${nfs4callbackSRCS})
add_sanitizers(nfs4callbacks)

