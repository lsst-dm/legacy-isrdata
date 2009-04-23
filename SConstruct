# -*- python -*-
#
# Setup our environment
#
import glob, os
import lsst.SConsUtils as scons

env = scons.makeEnv("isrdata",
                    r"$HeadURL: svn+ssh://svn.lsstcorp.org/DMS/testdata/isrdata/trunk/SConstruct $",
                    [])

Alias("install", [
    env.Install(env['prefix'], glob.glob("*.fits")),
    env.Install(os.path.join(env['prefix'], "CFHT", "D4", "dc3a"), [
            glob.glob(os.path.join("CFHT", "D4", "dc3a", "*.fits")),
            glob.glob(os.path.join("CFHT", "D4", "dc3a", "*.paf")),
        ]),
    env.Install(os.path.join(env['prefix'], "SimDeep", "dc3a"), [
        glob.glob(os.path.join("SimDeep", "dc3a", "*.fits")),
        glob.glob(os.path.join("SimDeep", "dc3a", "*.paf")),
    ]),
    env.InstallEups(env['prefix'] + "/ups", glob.glob("ups/*.table")),
])

scons.CleanTree(r"*~ core *.so *.os *.o")

env.Declare()

env.Help("""
Test data for ip_isr
""")
