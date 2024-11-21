PzAlipAgencyDashboardPartialExtract
PzNbAgencyDashboardPartialExtract
nb_agency_dashboard_partial_extract
$$EscapeParameter = idmcconv
fact_producer_ledger

****************************************************

PzFactNbSurgery_1
PzFactNbSurgery_2
PzFactNbSurgery_3
PzFactNbSurgery_SrcRecs1
PzFactNbSurgery_SrcRecs2	fact_nb_surgery

***********************************************

PzFactNbPersonalFinancial_1
PzFactNbPersonalFinancial_2
PzFactNbPersonalFinancial_3
PzFactNbPersonalFinancial_4


PzFactNbHospitalEmergency_pvt_1
PzFactNbHospitalEmergency_pvt_2
PzFactNbHospitalEmergency_pvt_3	fact_nb_hospital_emergency

********************************************************


PzFactNbCntInsuredPegaTrans	fact_nb_cnt_insured_pega_trans

************************************************************

update pdm_conv.brg_nb_cnt_dcln_reason
set chksum=upper(MD5(
NVL(agent_rsn_desc,'')||
NVL(cnt_id_nk,'')||
NVL(CAST(dcln_nb_rsn_sk as Varchar),'')||
NVL(dcln_rsn_cd,'')||
NVL(dcln_rsn_desc,'')||
NVL(to_char(dcln_rsn_eff_end_dt as Varchar,'YYYY-MM-DD'),'')||
NVL(to_char(dcln_rsn_eff_start_dt as Varchar,'YYYY-MM-DD'),'')||
NVL(CAST(dcln_rsn_ordr_num as Varchar),'')||
NVL(dcln_tp_cd,'')||
NVL(dcln_tp_desc,'')||
NVL(due_rsn_desc,'')||
NVL(edh_record_status_in,'')||
NVL(CAST(fact_nb_uw_cnt_insured_bnft_sk as Varchar),'')||
NVL(fcra_cd,'')||
NVL(fcra_rsn_cd,'')||
NVL(CAST(fcra_rsn_eff_end_dt as Varchar),'')||
NVL(CAST(fcra_rsn_eff_start_dt as Varchar),'')||
NVL(CAST(fcra_rsn_ordr_num as Varchar),'')||
NVL(insured_rsn_desc,'')||
NVL(is_curr_yn_ind,'')||
NVL(multi_fcra_rsn_desc,'')||
NVL(other_dcln_rsn_desc,'')||
NVL(reconsdr_period_txt,'')||
NVL(src_cl_id,'')||
NVL(CAST(src_cnt_bnft_link_ref_id as Varchar),'')||
NVL(CAST(src_cnt_rsn_ref_id as Varchar),'')||
NVL(src_rec_sts_cd,'')||
NVL(src_sys_nm_nk,'')))
WHERE edh_record_status_in IN ('A','D')
