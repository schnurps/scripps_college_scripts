#
#   Copyright 2012 Ricky Chilcott <chilcotr@ohio.edu>
#   with help from Geordie Korper <geordie@korper.org>
#
#   Licensed under the Apache License, Version 2.0 (the "License");
#   you may not use this file except in compliance with the License.
#       You may obtain a copy of the License at
#
#       http://www.apache.org/licenses/LICENSE-2.0
#
#   Unless required by applicable law or agreed to in writing, software
#   distributed under the License is distributed on an "AS IS" BASIS,
#   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
#   See the License for the specific language governing permissions and
#   limitations under the License.
#
# 
#  Luggage makefile for building a package that copies needed kickstart files for Munki

include /usr/local/share/luggage/luggage.make

TITLE=munki_kickstart
REVERSE_DOMAIN=edu.ohio.oit.pkg
PAYLOAD=pack-usr-local-munki-postflight\
        pack-usr-local-munki-preflight\
        pack-script-postflight
# PACKAGE_VERSION=1.0

l_usr_local_munki: l_usr_local
	@sudo mkdir -p ${WORK_D}/usr/local/munki
	@sudo chown root:wheel ${WORK_D}/usr/local/munki
	@sudo chmod 755 ${WORK_D}/usr/local/munki

pack-usr-local-munki-preflight: l_usr_local_munki
	@sudo ${INSTALL} -m 0755 -o root -g wheel munki_preflight ${WORK_D}/usr/local/munki/preflight

pack-usr-local-munki-postflight: l_usr_local_munki
	@sudo ${INSTALL} -m 0755 -o root -g wheel munki_postflight ${WORK_D}/usr/local/munki/postflight
