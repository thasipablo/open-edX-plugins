# Disable public account creation
#################################

from tutor import hooks

hooks.Filters.ENV_PATCHES.add_item(
    (
        "openedx-lms-common-settings",
        "FEATURES['ALLOW_PUBLIC_ACCOUNT_CREATION'] = False"
    )
)
