sasl_ntlm_sources = [
    'client-ntlm.c',
    'ntlmdes.c',
    'ntlm.h',
    'ntlmstruct.c',
]

if static_auth.contains('ntlm')
    foreach source : sasl_ntlm_sources
        sources += 'ntlm' / source
    endforeach
else
    ntlm_deps = [ntlmdep, ]

    sasl_ntlm = shared_module('ntlm', sasl_ntlm_sources,
                              name_prefix : 'sasl-',
                              dependencies : ntlm_deps,
                              include_directories : [include_dir, ],
                              install : true,
                              install_dir : auth_plugin_dir)
    clients += sasl_ntlm
endif