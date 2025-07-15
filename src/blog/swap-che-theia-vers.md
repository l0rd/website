---
title: 'Update a Che plugin sidecar on the fly'
date: '2020-10-13'
layout: "base.njk"
---

The following script allow to update a sidecar in Che plugin registry on the fly:

   ```bash
   # Set the namespace where CRW got deployed
   CRW_SERVER_NAMESPACE=workspaces-server

   # Set the Plugin Registry Pod name
   PLUGIN_REG_POD=plugin-registry-579847b4bf-r6m92

   # Set the path of meta.yaml we want to edit
   META_YAML_PATH=/var/www/html/v3/plugins/eclipse/che-theia/7.16.2/meta.yaml

   # Set the old image details
   OLD_IMAGE_REPO=registry.redhat.io/codeready-workspaces/theia-rhel8
   OLD_IMAGE_SHA=ddd13bee6b6e1c7d3c8b66f977801370c14150326f6f456e3ff0516cff5d0549
   OLD_IMAGE=${OLD_IMAGE_REPO}@sha256:${OLD_IMAGE_SHA}

   # Set the new image details
   NEW_IMAGE_REPO=quay.io/crw/theia-rhel8
   NEW_IMAGE_SHA=q09c02313a805f8d6049b747ed24c4e8cf1c7889fd78d915942f4e178b6d65c02
   NEW_IMAGE=${NEW_IMAGE_REPO}@sha256:${NEW_IMAGE_SHA}

   # Replace
   oc rsh -n ${CRW_SERVER_NAMESPACE} pod/${PLUGIN_REG_POD} \
      sed -i s+${OLD_IMAGE}+${NEW_IMAGE}+g ${THEIA_META_PATH}

   # Repeat
   OLD_IMAGE_REPO=registry.redhat.io/codeready-workspaces/theia-endpoint-rhel8
   OLD_IMAGE_SHA=434278f521fceca36f651700a2138f3a6a8565d56651719a658c29481725ce5e
   OLD_IMAGE=${OLD_IMAGE_REPO}@sha256:${OLD_IMAGE_SHA}
   NEW_IMAGE_REPO=quay.io/crw/theia-endpoint-rhel8
   NEW_IMAGE_SHA=9fb81f1566d04e4cb9d273a6ec654aa1f2e21e866729ed6bd038842be91ac3d3
   NEW_IMAGE=${NEW_IMAGE_REPO}@sha256:${NEW_IMAGE_SHA}
   oc rsh -n ${CRW_SERVER_NAMESPACE} pod/${PLUGIN_REG_POD} \
      sed -i s+${OLD_IMAGE}+${NEW_IMAGE}+g ${THEIA_META_PATH}
   ```